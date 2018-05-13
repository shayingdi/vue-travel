<template>
  <div class="home">
    <home-header></home-header>
  </div>
</template>

<script>
  // 多页应用，首屏时间快，seo效果好，但页面切换慢
  // 单页应用，页面切换快，首屏时间稍慢，seo差
  import HomeHeader from './components/Header.vue'
  export default {
    name: 'Home',
    components: {
      HomeHeader
    }
  }
</script>

<style>

</style>
