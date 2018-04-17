<template>
<div class="header">
  <div class="header-left">
    <span class="iconfont back-icon icon-fanhui"></span>
  </div>
  <div class="header-input">
    <span class="iconfont icon-sousuo"></span>请输入城市/景点/游玩主题
  </div>
  <div class="header-right">
    城市 <span class="iconfont icon-jiantou"></span>
  </div>
</div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@css/varibles.styl'
  .header
    display flex
    height: .88rem
    background: $bgColor
    line-height .88rem
    color #fff
    .header-left
      width .8rem
      text-align center
      .back-icon
        font-size: .36rem
    .header-input
      flex: 1
      color: #e4e7ea
      margin .14rem 0
      background #ffffff
      border-radius: .12rem
      line-height .6rem
      padding-left .2rem
      box-sizing: border-box
      .iconfont
        margin-right .1rem
    .header-right
      width 1.32rem
      text-align center
      .iconfont
        font-size: .24rem;
        margin-left: .04rem;
</style>
