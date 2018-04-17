<template>
<div id="container">
  <home-header :city="city"></home-header>
  <home-swiper :list="swiperList"></home-swiper>
  <home-category :list="categoryList"></home-category>
  <home-recommend :list="recommendList"></home-recommend>
  <home-weekend :list="weekendList"></home-weekend>
</div>
</template>

<script>
import HomeHeader from './components/header'
import HomeSwiper from './components/swiper'
import HomeCategory from './components/category'
import HomeRecommend from './components/recommend'
import HomeWeekend from './components/weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeCategory,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      categoryList: [],
      recommendList: [],
      weekendList: []
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/indexInfo')
        .then(this.getHomeInfoSucc)
        .catch((error) => {
          console.log(error)
        })
    },
    getHomeInfoSucc (res) {
      console.log(res)
      if (res.data.code === 200) {
        const data = res.data.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.categoryList = data.categoryList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  }
}
</script>

<style lang="stylus">
  #container
    background #f5f5f5
</style>
