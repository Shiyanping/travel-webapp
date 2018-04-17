<template>
<div class="cate-content">
  <swiper :options="swiperOption" ref="mySwiper" v-if="showSwiper">
    <swiper-slide v-for="(page, $index) of pages" :key="$index">
      <div class="category-item" v-for="item of page" :key="item.id">
        <img :src="item.img" :alt="item.name">
        <p v-text="item.name"></p>
      </div>
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination category-pagination" slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeCategory',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        speed: 1500
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((value, index) => {
        let page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(value)
      })
      return pages
    },
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@css/varibles.styl'
  @import '~@css/mixins.styl'
  .cate-content >>> .swiper-pagination-bullet-active
    background rgba(0,175,190,.8)!important
  .cate-content >>> .swiper-pagination-bullet
    width 6px
    height 6px
  .cate-content >>> .swiper-container
    height 100%
  .cate-content
    height 3.7rem
    padding-top .1rem
    background #fff
    overflow hidden
    .category-item
      float left
      width 25%
      height 1.3rem
      padding-top .3rem
      text-align center
      > img
        width .66rem
        height .66rem
      > p
        width 100%
        text-align center
        font-size .28rem
        margin-top .2rem
        color $fontBlackColor
        ellipsis()
</style>
