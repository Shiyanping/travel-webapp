<template>
  <div class="search">
    <input type="text" placeholder="请输入地名或拼音" class="search-input">
  </div>
</template>

<script>
export default {
  name: 'search'
}
</script>

<style lang="stylus" scoped>
  @import '~@css/varibles.styl'
  .search
    height .72rem
    background $bgColor
    padding .1rem
    .search-input
      color $fontBlackColor
      width 100%
      padding 0 .1rem
      box-sizing border-box
      height 100%
      text-align center
      border-radius .08rem
</style>
