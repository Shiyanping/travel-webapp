<template>
<div class="wrapper">
  <swiper :options="swiperOption" ref="mySwiper">
    <!-- slides -->
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" alt="">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000,
        speed: 1500
      },
      swiperList: [{
        id: 1,
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/1b/6c766b79e2045102.jpg_640x200_3e44c74a.jpg'
      }, {
        id: 2,
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/f8/300474f00e42aa02.jpg_640x200_b4884104.jpg'
      }, {
        id: 3,
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/75/58e0323d8e55902.jpg_640x200_d98a5f6a.jpg'
      }, {
        id: 4,
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b1/54862f4b1501e202.jpg_640x200_886ddf82.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff!important
  .wrapper >>> .swiper-pagination-bullet
    width: 6px
    height: 6px
  .wrapper
    overflow: hidden
    height: 0
    width: 100%
    padding-bottom 31.25%
    background-color: #ccc
    .swiper-img
      max-width: 100%
</style>
