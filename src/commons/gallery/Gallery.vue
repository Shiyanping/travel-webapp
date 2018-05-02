<template>
  <div class="container" @click="closeGallery">
    <swiper :options="swiperOption" class="swiper">
      <!-- slides -->
      <swiper-slide v-for="(item, $index) of imgList" :key="$index" class="swiper-item">
        <img class="swiper-img" :src="item">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'gallery',
  props: {
    imgList: {
      type: Array,
      default() {
        return [];
      }
    }
  },
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    };
  },
  methods: {
    closeGallery() {
      this.$emit('closeGallery');
    }
  }
};
</script>

<style lang="stylus" scoped>
.container
  position fixed
  top 0
  bottom 0
  left 0
  right 0
  background #000
  z-index 999
  .swiper
    height 100%
    .swiper-item
      position relative
      img
        position absolute
        top 50%
        transform translateY(-50%)
        max-width 100%
    .swiper-pagination
      color #fff
      bottom 1.2rem
</style>
