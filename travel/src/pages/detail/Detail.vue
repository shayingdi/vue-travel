<template>
  <div>
    <banner-detail></banner-detail>
    <banner-header></banner-header>
    <div class="content"></div>
  </div>
</template>

<script>
  import BannerDetail from './components/Banner'
  import BannerHeader from './components/Header.vue'
  export default {
    name: 'Detail',
    components: {
      BannerDetail,
      BannerHeader
    }
  }
</script>

<style lang="stylus" scoped>
  .content 
    height 50rem
</style>


