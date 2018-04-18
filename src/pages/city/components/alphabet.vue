<template>
  <ul class="list">
    <li>A</li>
    <li>A</li>
    <li>A</li>
    <li>A</li>
    <li>A</li>
    <li>A</li>
    <li>A</li>
    <li>A</li>
    <li>A</li>
  </ul>
</template>

<script>
export default {
  name: 'alphabet'
}
</script>

<style lang="stylus" scoped>
  @import '~@css/varibles.styl'
  .list
    display flex
    position absolute
    right 0
    top 50%
    transform translateY(-50%)
    bottom 0
    width .6rem
    text-align center
    justify-content center
    flex-direction column
    li
      color $bgColor
      font-size .32rem
      line-height .4rem
</style>
