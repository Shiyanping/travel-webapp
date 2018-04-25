<template>
  <div>
    <div class="search">
      <input v-model="keyword" type="text" placeholder="请输入地名或拼音" class="search-input">
    </div>
    <div class="search-list" ref="search-list" v-show="keyword">
      <ul>
        <li v-for="item of searchList" :key="item.id" class="border-bottom" @click="handleClickCity(item.name)">
          {{item.name}}
        </li>
        <li v-show="noDataShow">暂无相关数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll';
import { mapMutations } from 'vuex';
export default {
  name: 'search',
  props: {
    cities: Object
  },
  data() {
    return {
      keyword: '',
      timer: null,
      searchList: []
    };
  },
  computed: {
    noDataShow() {
      return !this.searchList.length;
    }
  },
  mounted() {
    this.$nextTick(() => {
      var element = this.$refs['search-list'];
      this.scroll = new BScroll(element);
    });
  },
  methods: {
    ...mapMutations({
      changeCity: 'changeCity'
    }),
    handleClickCity(name) {
      this.changeCity(name);
      this.$router.push('/');
    }
  },
  watch: {
    keyword() {
      if (this.timer) {
        clearTimeout(this.timer);
      }
      if (!this.keyword) {
        this.searchList = [];
      }
      this.timer = setTimeout(() => {
        const result = [];
        for (let i in this.cities) {
          this.cities[i].forEach((value, index) => {
            if (
              value.name.indexOf(this.keyword) > -1 ||
              value.spell.indexOf(this.keyword) > -1
            ) {
              result.push(value);
            }
          });
        }
        this.searchList = result;
      }, 100);
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~@css/varibles.styl'
.search
  height 0.72rem
  background $bgColor
  padding 0.1rem
  .search-input
    color $fontBlackColor
    width 100%
    padding 0 0.1rem
    box-sizing border-box
    height 100%
    text-align center
    border-radius 0.08rem
.search-list
  position absolute
  background #eee
  top 1.8rem
  bottom 0
  left 0
  right 0
  z-index 1
  overflow hidden
  li
    line-height 0.7rem
    height 0.7rem
    background #fff
    color $fontBlackColor
    padding-left 0.4rem
</style>
