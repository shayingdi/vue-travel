<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-title">
          {{this.sightName}}
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe632;</span>{{this.bannerImgs.length}}
        </div>
      </div>
    </div>
    <fade><common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary></fade>
  </div>
</template>

<script>
  import commonGallary from 'common/gallary/Gallary'
  import Fade from 'common/fade/Fade'
  export default {
    name: 'DetailBanner',
    props: {
      sightName: String,
      bannerImg: String,
      bannerImgs: Array
    },
    data() {
      return {
        //imgs: ['http://img1.qunarzz.com/sight/p0/201403/07/552f3468861a6052c0b6ba77d255e558.jpg_r_800x800_7949fb53.jpg', 'http://img1.qunarzz.com/sight/p0/1502/b0/b0a7120b77c5a6ad.water.jpg_350x240_81beb7bf.jpg'],
        showGallary: false
      }
    },
    methods: {
      handleBannerClick() {
        this.showGallary = true
      },
      handleGallaryClose() {
        this.showGallary = false
      }
    },
    components: {
      commonGallary,
      Fade
    },
  }
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    height 0
    overflow hidden
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      background-image linear-gradient(top, rgba(0,0,0,0),rgba(0,0,0,0.8))
      .banner-title
        flex 1
        font-size .32rem
        padding 0 .2rem
      .banner-number
        margin-top .12rem
        padding 0 .32rem
        line-height .32rem
        height .4rem
        border-radius .2rem
        background-color rgba(0,0,0,.8)
        font-size .24rem
        .banner-icon
          font-size .24rem
</style>


