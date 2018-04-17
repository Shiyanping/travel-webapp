<template>
<div class="wrapper">
  <swiper :options="swiperOption" ref="mySwiper" v-if="showSwiper">
    <!-- slides -->
    <swiper-slide v-for="item of list" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" alt="">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000,
        speed: 1500
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
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
