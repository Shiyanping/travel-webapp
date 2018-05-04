<template>
  <div class="container">
    <detail-banner :bannerImg="bannerImg" :gallaryImgs="gallaryImgs" :title="title"></detail-banner>
    <detail-header></detail-header>
    <detail-list :list="list"></detail-list>
  </div>
</template>

<script>
import DetailBanner from './components/DetailBanner';
import DetailHeader from './components/DetailHeader';
import DetailList from './components/List';
import axios from 'axios';
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data() {
    return {
      list: [],
      title: '',
      gallaryImgs: [],
      bannerImg: ''
    };
  },
  mounted() {
    this.getDetailInfo();
  },
  methods: {
    getDetailInfo() {
      axios
        .get('/api/detail', {
          params: {
            id: this.$route.params.id
          }
        })
        .then(this.getDetailSucc);
    },
    getDetailSucc(res) {
      console.log(res);
      let data = res.data;
      if (data.code === 200) {
        this.list = data.data.categoryList;
        this.title = data.data.sightName;
        this.gallaryImgs = data.data.gallaryImgs;
        this.bannerImg = data.data.bannerImg;
      }
    }
  }
};
</script>

<style lang="stylus" scoped>
</style>
