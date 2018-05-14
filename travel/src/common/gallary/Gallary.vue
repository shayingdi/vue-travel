<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for=" (item,index) in imgs" :key="index">
          <img class="swiper-img" :src="item" alt="">
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'commonGallary',
    props: {
      imgs: Array
    },
    data() {
      return {
        swiperOption: {
          pagination: '.swiper-pagination',
          paginationType: 'fraction',
          loop: true,
          observeParents: true,
          observer: true
        }
      }
    },
    methods: {
      handleGallaryClick(){
        this.$emit('close')
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow inherit
  .container
    position fixed 
    left 0
    top 0
    right 0
    bottom 0
    z-index 99
    display flex
    flex-direction column
    justify-content center
    background-color #000
    .wrapper
      width 100%
      height 0
      padding-bottom 100%
      .swiper-img
        width 100%
      .swiper-pagination
        color #fff
        bottom -1rem
</style>


