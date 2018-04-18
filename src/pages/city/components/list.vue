<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <ul class="city-list">
          <li class="city-wrapper">
            <a href="javascript:void(0)" class="city-button">北京</a>
          </li>
        </ul>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <ul class="city-list">
          <li class="city-wrapper" v-for="item of hot" :key="item.id">
            <a href="javascript:void(0)" class="city-button">{{item.name}}</a>
          </li>
        </ul>
      </div>
      <div
        class="area"
        v-for="(item, key) of cities"
        :key="key"
        :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <ul class="scroll-list">
          <li
            class="list-item border-bottom"
            v-for="cityItem of item"
            :key="cityItem.id">
            {{cityItem.name}}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'list',
  props: {
    cities: Object,
    hot: Array,
    letter: String
  },
  mounted () {
    this.$nextTick(() => {
      this.scroll = new BScroll(this.$refs.wrapper, {})
    })
  },
  watch: {
    letter () {
      if (this.letter !== '') {
        let element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@css/varibles.styl'
  .border-topbottom
    &:before
      background-color #ccc
    &:after
      background-color #ccc
  .border-bottom
    &:before
      background-color #eee
  .list
    position absolute
    top 1.8rem
    right 0
    bottom 0
    left 0
    overflow hidden
    .title
      padding .24rem .3rem
      color $fontBlackColor
      font-size .24rem
      background #f5f5f5
    .city-list
      overflow hidden
      padding .2rem .6rem 0 .2rem
      .city-wrapper
        float left
        width 33.3%
        margin-bottom .2rem
        .city-button
          display block
          padding .1rem
          color $fontBlackColor
          border .02rem solid #ccc
          text-align center
          border-radius .08rem
          margin-right .2rem
    .scroll-list
      overflow hidden
      .list-item
        height .6rem
        line-height .6rem
        padding .1rem .6rem .1rem .2rem
</style>
