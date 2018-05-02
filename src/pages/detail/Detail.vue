<template>
  <div class="container">
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <detail-list :list="list"></detail-list>
  </div>
</template>

<script>
import DetailBanner from './components/DetailBanner';
import DetailHeader from './components/DetailHeader';
import DetailList from './components/List';
export default {
  name: 'detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data() {
    return {
      list: [
        {
          name: '门票',
          children: [
            {
              name: '成人票',
              price: 17.9
            },
            {
              name: '学生票',
              price: 17.9
            },
            {
              name: '老人票',
              price: 17.9
            }
          ]
        },
        {
          name: '家庭票',
          children: [
            {
              name: '亲子票（2大1小）',
              price: 17.9
            },
            {
              name: '亲子票（1大1小）',
              price: 17.9
            }
          ]
        },
        {
          name: '套票',
          children: [
            {
              name: '自驾车票+家庭套票（2大1小）',
              price: 17.9
            },
            {
              name: '自驾车票+双成人套票',
              price: 17.9
            }
          ]
        },
        {
          name: '一日游',
          children: [
            {
              name: '自驾车票+家庭套票（2大1小）',
              price: 17.9
            },
            {
              name: '自驾车票+双成人套票',
              price: 17.9
            },
            {
              name: '自驾车票+家庭套票（2大1小）',
              price: 17.9
            }
          ]
        },
        {
          name: '门票',
          children: [
            {
              name: '成人票',
              price: 17.9
            },
            {
              name: '学生票',
              price: 17.9
            },
            {
              name: '老人票',
              price: 17.9
            }
          ]
        }
      ]
    };
  }
};
</script>

<style lang="stylus" scoped>
</style>
