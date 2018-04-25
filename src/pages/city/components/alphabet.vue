<template>
  <ul class="list">
    <li v-for="item of list" :key="item" :ref="item" @click="clickAlpabet" @touchstart="handleTouchStart" @touchmove="handleTouchMove" @touchend="handleTouchEnd">
      {{item}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'alphabet',
  props: {
    cities: Object
  },
  data() {
    return {
      // 判断是否在活动过程中
      touchStart: false,
      startY: 0,
      timer: null
    };
  },
  updated() {
    this.startY = this.$refs['A'][0].offsetTop;
  },
  methods: {
    clickAlpabet(e) {
      this.$emit('change', e.target.innerText);
    },
    handleTouchStart() {
      this.touchStart = true;
    },
    handleTouchMove(e) {
      if (this.touchStart) {
        // 函数节流
        if (this.timer) {
          clearTimeout(this.timer);
        }
        this.timer = setTimeout(() => {
          let endY = e.touches[0].clientY - 175;
          let scrollIndex = Math.floor((endY - this.startY) / 20);
          if (scrollIndex >= 0 && scrollIndex < this.list.length) {
            this.$emit('change', this.list[scrollIndex]);
          }
        }, 16);
      }
    },
    handleTouchEnd() {
      this.touchStart = false;
    }
  },
  computed: {
    list() {
      const list = [];
      for (let key in this.cities) {
        list.push(key);
      }
      return list;
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~@css/varibles.styl'
.list
  display flex
  position absolute
  right 0
  top 3.5rem
  width 0.6rem
  justify-content center
  flex-direction column
  li
    color $bgColor
    font-size 0.28rem
    line-height 0.4rem
    width 100%
    text-align center
</style>
