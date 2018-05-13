<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item in swiperList" :key="item.id">
        <img class="swiper-img" :src='item.img' alt="">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: 'HomeSwiper',
    data() {
      return {
        swiperOption: {
          pagination: '.swiper-pagination',
          loop: true
        },
        swiperList: [{
            id: '001',
            img: 'http://img1.qunarzz.com/piao/fusion/1804/15/9250dbc86a456302.jpg_750x200_b423f532.jpg'
          },
          {
            id: '002',
            img: 'http://img1.qunarzz.com/piao/fusion/1805/9a/c0984ec80d0f0a02.jpg_750x200_f55672ab.jpg'
          },
          {
            id: '003',
            img: 'http://img1.qunarzz.com/piao/fusion/1805/9e/f625886dec6c0402.jpg_750x200_417be630.jpg'
          }
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background-color #fff
  .wrapper
    width 100%
    height 0
    overflow hidden
    padding-bottom 31.25%
    .swiper-img
      width 100%
</style>

