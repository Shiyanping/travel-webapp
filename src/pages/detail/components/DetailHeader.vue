<template>
  <div>
    <router-link tag="div" class="header-abs" to="/" v-show="!showFixed">
      <span class="iconfont icon-fanhui"></span>
    </router-link>
    <div class="header-fixed" v-show="showFixed" :style="fixedStyle">
      <router-link tag="div" class="header-left" to="/">
        <span class="iconfont icon-fanhui"></span>
      </router-link>
      {{detailTitle}}
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'detailHeader',
  data() {
    return {
      showFixed: false,
      fixedStyle: {
        opacity: 0
      }
    };
  },
  computed: {
    ...mapState(['detailTitle'])
  },
  methods: {
    handleScroll() {
      let scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
      if (scrollTop > 60) {
        let opacity = scrollTop / 140 > 1 ? 1 : scrollTop / 140;
        this.fixedStyle = { opacity };
        this.showFixed = true;
      } else {
        this.showFixed = false;
      }
    }
  },
  activated() {
    window.addEventListener('scroll', this.handleScroll);
  },
  deactivated() {
    window.removeEventListener('scroll', this.handleScroll);
  }
};
</script>

<style lang="stylus" scoped>
@import '~@css/varibles.styl'
.header-abs
  position absolute
  left 0.1rem
  color #fff
  text-align center
  top 0.1rem
  width 0.72rem
  height 0.72rem
  line-height 0.72rem
  font-size 0.36rem
  background-color rgba(0, 0, 0, 0.5)
  border-radius 50%
  .icon-fanhui
    font-weight 900
.header-fixed
  position fixed
  top 0
  left 0
  right 0
  height $headerHeight
  background $bgColor
  line-height $headerHeight
  color #fff
  text-align center
  z-index 999
  .header-left
    position absolute
    left 0
    width 0.8rem
    text-align center
    .icon-fanhui
      font-size 0.36rem
</style>
