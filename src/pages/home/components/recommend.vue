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
            <div>查看详情
              <span class="iconfont icon-right"></span>
            </div>
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
  data() {
    return {};
  }
};
</script>

<style lang="stylus" scoped>
@import '~@css/varibles.styl'
.recommend
  margin-top 0.2rem
  background #fff
  .title
    padding 0.24rem 0
    height 0.44rem
    color #212121
    font-size 0.32rem
    line-height 0.44rem
    .icon-xin
      margin-right 0.04rem
      width 0.3rem
      height 0.3rem
      margin-left 0.2rem
      color #ff5a58
  .list
    margin-left 0.24rem
    .item
      display flex
      overflow hidden
      padding 0.2rem 0
      > img
        width 2rem
        height 2rem
      .item-detail
        flex 1
        padding-left 0.22rem
        .item-title
          margin-top 0.26rem
          height 0.44rem
          color $fontBlackColor
          font-size 0.32rem
          line-height 0.44rem
        .item-comment
          margin-top 0.14rem
          height 0.34rem
          color $subFontBlackColor
          font-size 0.24rem
          line-height 0.34rem
        .open-item
          display flex
          margin-top 0.22rem
          color $subFontBlackColor
          font-size 0.24rem
          height 0.4rem
          line-height 0.4rem
          justify-content space-between
          align-items center
          padding-right 0.2rem
          > div
            color #555
            .icon-right
              font-size 0.2rem
              margin-left 0.04rem
</style>
