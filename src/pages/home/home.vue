<template>
<div id="container">
  <home-header></home-header>
  <home-swiper></home-swiper>
  <home-category></home-category>
  <home-recommend></home-recommend>
</div>
</template>

<script>
import HomeHeader from './components/header'
import HomeSwiper from './components/swiper'
import HomeCategory from './components/category'
import HomeRecommend from './components/recommend'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeCategory,
    HomeRecommend
  }
}
</script>

<style lang="stylus">
  #container
    background #f5f5f5
</style>
