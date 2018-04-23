<template>
  <div class="recommend">
    <div class="title">
      <span class="iconfont icon-huo"></span> 周末去哪玩
    </div>
    <ul class="list">
      <li class="item" v-for="item of list" :key="item.id">
        <div class="item-img-box">
          <img :src="item.img" :alt="item.name">
        </div>
        <div class="item-detail">
          <p class="item-title" v-text="item.name"></p>
          <p class="item-desc" v-text="item.desc"></p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
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
@import '~@css/mixins.styl'

.recommend
  margin-top 0.2rem
  background #fff

  .title
    padding 0.24rem 0
    height 0.44rem
    color #212121
    font-size 0.32rem
    line-height 0.44rem

    .icon-huo
      margin-right 0.04rem
      width 0.3rem
      height 0.3rem
      margin-left 0.2rem
      color #ff5a58

  .list
    background #f5f5f5

  .item
    margin-bottom 0.1rem
    background #fff

    .item-img-box
      overflow hidden
      height 0
      padding-bottom 37.4375%

    > img
      width 100%

    .item-detail
      padding 0.14rem 1.6rem 0.2rem 0.2rem

      .item-title
        color $fontBlackColor
        font-size 0.28rem
        line-height 0.48rem
        ellipsis()

      .item-desc
        color $subFontBlackColor
        font-size 0.24rem
        line-height 0.42rem
        ellipsis()
</style>
