<template>
<div class="recommend">
  <div class="title">
    <span class="iconfont icon-xin"></span> 猜你喜欢
  </div>
  <ul class="list">
    <li class="item border-bottom" v-for="item of list" :key="item.id">
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
  props: {
    list: Array
  },
  data () {
    return {}
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
