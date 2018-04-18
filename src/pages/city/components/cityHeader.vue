<template>
  <div class="city-header">
    <router-link to="/">
      <div class="header-left">
        <span class="iconfont icon-fanhui"></span>
      </div>
    </router-link>
    选择城市
  </div>
</template>

<script>
export default {
  name: 'cityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@css/varibles.styl'
  .city-header
    position relative
    height $headerHeight
    line-height $headerHeight
    color #ffffff
    text-align center
    background: $bgColor
    .header-left
      position absolute
      top 0
      left 0
      width .8rem
      text-align center
      height 100%
      .icon-fanhui
        font-size: .36rem
        color #fff
</style>
