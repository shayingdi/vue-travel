<template>
  <div class="header">
    <router-link to="/" class="header-abs" tag="div" v-show="showAbs"><span class="iconfont back-icon">&#xe624;</span></router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <span class="iconfont back-icon">&#xe624;</span> 景点详情
    </div>
  </div>
</template>

<script>
  export default {
    name: 'DetailHeader',
    data() {
      return {
        showAbs: true,
        opacityStyle: {
          opacity: 0
        }
      }
    },
    methods: {
      handleScroll() {
        const top = document.documentElement.scrollTop
        if (top > 60) {
          const opacityNum = top / 140
          //console.log(opacityNum)
          //opacity = opacity > 1 ? 1 : opacity
          this.opacityStyle = {
            opacity: opacityNum
          }
          this.showAbs = false
        } else {
          this.showAbs = true
        }
      }
    },
    activated() {
      window.addEventListener('scroll', this.handleScroll)
    },
    deactivated() {
      window.removeEventListener('scroll', this.handleScroll)
    }
  }
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
  .header-abs
    position absolute
    left .2rem
    top .2rem
    width .8rem
    height .8rem
    border-radius .4rem
    background-color rgba(0,0,0,.8)
    text-align center
    line-height .8rem
    .back-icon
      font-size .4rem
      color #fff
  .header-fixed
    position fixed
    left 0
    top 0
    right 0
    height $headerHeight
    line-height $headerHeight
    text-align center
    color #fff
    background-color $bgColor
    font-size .32rem
    z-index 99
    .back-icon
      position absolute
      width .64rem
      text-align center
      font-size .4rem
      top 0
      left 0
      color #fff
</style>
