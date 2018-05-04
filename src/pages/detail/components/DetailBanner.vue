<template>
  <div>
    <div class="banner" @click="handleClickBanner">
      <img :src="bannerImg" alt="">
      <div class="banner-img-num">
        <span class="iconfont icon-tupian"></span> {{gallaryImgs.length}}
      </div>
      <div class="banner-title">{{title}}</div>
    </div>
    <common-gallery :imgList="gallaryImgs" v-show="showGallery" @closeGallery="handleCloseGallery"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from '@commons/gallery/Gallery';
export default {
  name: 'detailBanner',
  props: {
    bannerImg: String,
    gallaryImgs: Array,
    title: String
  },
  components: {
    CommonGallery
  },
  data() {
    return {
      showGallery: false
    };
  },
  methods: {
    handleClickBanner() {
      this.showGallery = true;
    },
    handleCloseGallery() {
      this.showGallery = false;
    }
  }
};
</script>

<style lang="stylus" scoped>
.banner
  position relative
  width 100%
  height 0
  overflow hidden
  padding-bottom 55%
  .banner-img-num, .banner-title
    position absolute
    left 0.1rem
    color #fff
    text-align center
  img
    max-width 100%
  .banner-img-num
    bottom 0.86rem
    width 1.2rem
    height 0.4rem
    background rgba(0, 0, 0, 0.5)
    border-radius 0.2rem
    font-size 0.24rem
    .icon-tupian
      position relative
      top 0.025rem
  .banner-title
    line-height 0.4rem
    font-size 0.36rem
    bottom 0.36rem
    left 0.2rem
    right 0.2rem
    text-shadow 0 1px 2px rgba(0, 0, 0, 0.7)
    text-align left
</style>
