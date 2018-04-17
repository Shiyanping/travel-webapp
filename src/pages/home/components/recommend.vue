<template>
<div class="recommend">
  <div class="title">
    <span class="iconfont icon-xin"></span> 猜你喜欢
  </div>
  <ul class="list">
    <li class="item border-bottom" v-for="item of categoryList" :key="item.id">
      <img :src="item.img" alt="">
      <div class="item-detail">
        <p class="item-title" v-text="item.name"></p>
        <p class="item-comment" v-text="item.commentCount + '条评论'"></p>
        <div class="open-item">
          <span v-text="item.position"></span>
          <div>查看详情 <span class="iconfont icon-right"></span></div>
        </div>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      categoryList: [{
        id: 1,
        img: 'http://img1.qunarzz.com/sight/p0/1803/7b/7b023b9728f0834fa3.img.jpg_200x200_5fddc1d8.jpg',
        name: '世界花卉大观园',
        commentCount: 3727,
        position: '丰台区'
      }, {
        id: 2,
        img: 'http://img1.qunarzz.com/sight/p0/201403/10/b892e5069c3508f7b017a91121502223.jpg_200x200_3d7db4ec.jpg',
        name: '古北水镇',
        commentCount: 5417,
        position: '密云县'
      }, {
        id: 3,
        img: 'http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_200x200_0938a8f2.jpg',
        name: '北京野生动物园',
        commentCount: 8592,
        position: '大兴区'
      }, {
        id: 4,
        img: 'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_200x200_7690e4cd.jpg',
        name: '北京欢乐谷',
        commentCount: 52315,
        position: '朝阳区'
      }, {
        id: 5,
        img: 'http://img1.qunarzz.com/sight/p0/201308/08/41150dacc0e3a0c8c8d65eac.jpg_200x200_c62292e9.jpg',
        name: '北京动物园',
        commentCount: 3727,
        position: '西城区'
      }, {
        id: 6,
        img: 'http://img1.qunarzz.com/sight/p0/1602/68/68aa05adb5315f9990.water.jpg_200x200_ce3d2658.jpg',
        name: '北京海洋馆',
        commentCount: 1807,
        position: '西城区'
      }, {
        id: 7,
        img: 'http://img1.qunarzz.com/sight/p0/1505/9d/9d57a1306cb903cd.water.jpg_200x200_c6340318.jpg',
        name: '张裕爱斐堡',
        commentCount: 1059,
        position: '密云县'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@css/varibles.styl'
  .recommend
    margin-top .2rem
    background #fff
    .title
      padding .24rem 0
      height .44rem
      color #212121
      font-size .32rem
      line-height .44rem
      .icon-xin
        margin-right .04rem
        width .3rem
        height .3rem
        margin-left .2rem
        color #ff5a58
    .list
      margin-left .24rem
      .item
        display flex
        overflow hidden
        padding .2rem 0
        > img
          width 2rem
          height 2rem
        .item-detail
          flex 1
          padding-left .22rem
          .item-title
            margin-top .26rem
            height .44rem
            color $fontBlackColor
            font-size .32rem
            line-height .44rem
          .item-comment
            margin-top .14rem
            height .34rem
            color $subFontBlackColor
            font-size .24rem
            line-height .34rem
          .open-item
            display flex
            margin-top .22rem
            color $subFontBlackColor
            font-size .24rem
            height .4rem
            line-height .4rem
            justify-content space-between
            align-items center
            padding-right .2rem
            > div
              color #555
              .icon-right
                font-size .2rem
                margin-left .04rem
</style>
