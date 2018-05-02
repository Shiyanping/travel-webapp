<template>
  <div>
    <div v-for="(item, $index) of list" :key="$index">
      <div class="list-item border-bottom">
        <p class="item-title">{{item.name}}</p>
        <p class="item-price" v-if="item.price">{{item.price}}</p>
      </div>
      <div v-if="item.children" class="list-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'detailList',
  props: {
    list: Array
  }
};
</script>

<style lang="stylus" scoped>
.list-item
  display flex
  color #333
  font-size 0.32rem
  line-height 0.88rem
  padding 0 0.5rem 0 .2rem
  justify-content space-between
.list-children
  padding-left 0.2rem
</style>
