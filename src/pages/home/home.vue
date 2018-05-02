<template>
  <div id="container">
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-category :list="categoryList"></home-category>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header';
import HomeSwiper from './components/Swiper';
import HomeCategory from './components/Category';
import HomeRecommend from './components/Recommend';
import HomeWeekend from './components/Weekend';
import axios from 'axios';
import { mapState } from 'vuex';
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeCategory,
    HomeRecommend,
    HomeWeekend
  },
  data() {
    return {
      lastCity: '',
      swiperList: [],
      categoryList: [],
      recommendList: [],
      weekendList: []
    };
  },
  computed: {
    ...mapState(['city'])
  },
  mounted() {
    this.lastCity = this.city;
    this.getHomeInfo();
  },
  methods: {
    getHomeInfo() {
      axios
        .get('/api/indexInfo?city=' + this.city)
        .then(this.getHomeInfoSucc)
        .catch(error => {
          console.log(error);
        });
    },
    getHomeInfoSucc(res) {
      console.log(res);
      if (res.data.code === 200) {
        const data = res.data.data;
        // this.city = data.city;
        this.swiperList = data.swiperList;
        this.categoryList = data.categoryList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
      }
    }
  },
  activated() {
    if (this.lastCity !== this.city) {
      this.getHomeInfo();
      this.lastCity = this.city;
    }
  }
};
</script>

<style lang="stylus">
#container
  background #f5f5f5
</style>
