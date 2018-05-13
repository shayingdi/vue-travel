<template>
  <div class="icons">
    <swiper :options="swiperOption" >
      <swiper-slide v-for="(page) in pages" :key="page.index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: 'HomeIcons',
    props: {
      list: Array
    },
    data() {
      return {
        swiperOption: {
          pagination: '.swiper-pagination',
          loop: false
        }
      }
    },
    computed: {
      pages() {
        const pages = []
        this.list.forEach((item, index) => {
          const page = Math.floor(index / 8)
          if (!pages[page]) {
            pages[page] = []
          }
          pages[page].push(item)
        })
        return pages
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    width 100%
    height 0
    padding-bottom 50%
  .icons
    margin-top .1rem
    .icon 
      width 25%
      height 0
      float left
      padding-bottom 25%
      overflow hidden
      position relative
      .icon-img
        position absolute 
        left 0
        top 0
        bottom .44rem
        right 0
        box-sizing border-box
        padding .1rem
        img
          height 100%
          display block 
          margin 0 auto 
      .icon-desc
        position absolute
        bottom 0
        height .44rem
        line-height .44rem
        color $darkTextColor
        text-align center
        width 100%
        ellipsis()
</style>


