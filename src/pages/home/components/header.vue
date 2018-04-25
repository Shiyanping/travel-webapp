<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont icon-fanhui"></span>
    </div>
    <div class="header-input">
      <span class="iconfont icon-sousuo"></span>请输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{currentCity}}
        <span class="iconfont icon-jiantou"></span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex';
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState({
      currentCity: 'city'
    }),
    ...mapGetters(['doubleCity'])
  }
};
</script>

<style lang="stylus" scoped>
@import '~@css/varibles.styl'
.header
  display flex
  height $headerHeight
  background $bgColor
  line-height $headerHeight
  color #fff
  .header-left
    width 0.8rem
    text-align center
    .icon-fanhui
      font-size 0.36rem
  .header-input
    flex 1
    color #e4e7ea
    margin 0.14rem 0
    background #ffffff
    border-radius 0.12rem
    line-height 0.6rem
    padding-left 0.2rem
    box-sizing border-box
    .iconfont
      margin-right 0.1rem
  .header-right
    min-width 1.12rem
    text-align center
    color #fff
    padding 0 0.1rem
    .iconfont
      font-size 0.24rem
      margin-left 0.04rem
</style>
