<template>
  <div class="home">
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
  // 多页应用，首屏时间快，seo效果好，但页面切换慢
  // 单页应用，页面切换快，首屏时间稍慢，seo差
  import HomeHeader from './components/Header.vue'
  import HomeSwiper from './components/Swiper.vue'
  import HomeIcons from './components/Icons.vue'
  import HomeRecommend from './components/Recommend.vue'
  import HomeWeekend from './components/Weekend.vue'
  import axios from 'axios'
  export default {
    name: 'Home',
    components: {
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommend,
      HomeWeekend
    },
    data() {
      return {
        
        swiperList: [],
        iconList: [],
        recommendList: [],
        weekendList: []
      }
    },
    methods: {
      getHomeInfo() {
        axios.get('/api/index.json').then(this.GetHomeInfoSucc)
      },
      GetHomeInfoSucc(res) {
        res = res.data
        if (res.ret && res.data) {
          const data = res.data
          
          this.swiperList = data.swiperList
          this.iconList = data.iconList
          this.recommendList = data.recommendList
          this.weekendList = data.weekendList
        }
      }
    },
    mounted() {
      this.getHomeInfo()
    }
  }
</script>

<style>

</style>
