<template>
<div class="recommend">
  <div class="title">
    <span class="iconfont icon-huo"></span> 周末去哪玩
  </div>
  <ul class="list">
    <li class="item" v-for="item of categoryList" :key="item.id">
      <div class="item-img-box">
        <img :src="item.img" :alt="item.name">
      </div>
      <div class="item-detail">
        <p class="item-title" v-text="item.name"></p>
        <p class="item-desc" v-text="item.desc"></p>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      categoryList: [{
        id: 1,
        img: 'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        name: '北京赏花好地方',
        desc: '乱花渐欲迷人眼，京城赏花大搜索'
      }, {
        id: 2,
        img: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
        name: '北京必游TOP10',
        desc: '来北京必去的景点非这些地方莫属'
      }, {
        id: 3,
        img: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
        name: '寻找北京的皇城范儿',
        desc: '数百年的宫廷庙宇，至今依旧威严霸气'
      }, {
        id: 4,
        img: 'http://img1.qunarzz.com/sight/source/1505/ce/bc89bc2f0e33ea.jpg_r_640x214_3e408453.jpg',
        name: '学生最爱的博物馆',
        desc: '周末干嘛？北京很多博物馆已经免费开放啦'
      }, {
        id: 5,
        img: 'http://img1.qunarzz.com/sight/source/1505/b2/fde1bfcd057a52.jpg_r_640x214_bbf3fa44.jpg',
        name: '儿童剧场，孩子的乐园',
        desc: '带宝贝观看演出，近距离体验艺术的无穷魅力'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@css/varibles.styl'
  @import '~@css/mixins.styl'
  .recommend
    margin-top .2rem
    background #fff
    .title
      padding .24rem 0
      height .44rem
      color #212121
      font-size .32rem
      line-height .44rem
      .icon-huo
        margin-right .04rem
        width .3rem
        height .3rem
        margin-left .2rem
        color #ff5a58
    .list
      background: #f5f5f5
    .item
      margin-bottom .1rem
      background #fff
      .item-img-box
        overflow hidden
        height 0
        padding-bottom 37.4375%
      > img
        width 100%
      .item-detail
        padding .14rem 1.6rem .2rem .2rem
        .item-title
          color $fontBlackColor
          font-size .28rem
          line-height .48rem
          ellipsis()
        .item-desc
          color $subFontBlackColor
          font-size .24rem
          line-height .42rem
          ellipsis()
</style>
