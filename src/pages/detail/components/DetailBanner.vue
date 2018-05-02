<template>
  <div>
    <div class="banner" @click="handleClickBanner">
      <img src="http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_600x330_f68eb231.jpg" alt="">
      <div class="banner-img-num">
        <span class="iconfont icon-tupian"></span> 11
      </div>
      <div class="banner-title">{{detailTitle}}(AAAA景区)</div>
    </div>
    <common-gallery :imgList="bannerList" v-show="showGallery" @closeGallery="handleCloseGallery"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from '@commons/gallery/Gallery';
import { mapState } from 'vuex';
export default {
  name: 'detailBanner',
  components: {
    CommonGallery
  },
  computed: {
    ...mapState(['detailTitle'])
  },
  data() {
    return {
      showGallery: false,
      bannerList: [
        'http://img1.qunarzz.com/sight/p0/1501/7d/bf80dd42eea3649a9fcb126bc9b594ba.water.jpg_r_800x800_8d93aab4.jpg',
        'http://img1.qunarzz.com/sight/p0/1507/cc/19733fc0135062788140cbb48ae606a7.water.jpg_r_800x800_6129f4dd.jpg'
      ]
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
