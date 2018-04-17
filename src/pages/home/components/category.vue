<template>
<div class="cate-content">
  <swiper :options="swiperOption" ref="mySwiper">
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        speed: 1500
      },
      categoryList: [{
        id: 1,
        name: '景点门票',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
      }, {
        id: 2,
        name: '必游榜单',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/54/35899492b1302802.png'
      }, {
        id: 3,
        name: '踏青赏花',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png'
      }, {
        id: 4,
        name: '动植物园',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png'
      }, {
        id: 5,
        name: '故宫',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png'
      }, {
        id: 6,
        name: '古北水镇',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png'
      }, {
        id: 7,
        name: '定制游',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/fa/fe1915e1d20bcc02.png'
      }, {
        id: 8,
        name: '一日游',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/c1/ac058f238b9a6802.png'
      }, {
        id: 9,
        name: '自然风光',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png'
      }, {
        id: 10,
        name: '演出',
        img: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.categoryList.forEach((value, index) => {
        let page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(value)
      })
      return pages
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
