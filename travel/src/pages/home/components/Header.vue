<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市、景点、游玩主题</div>
    <router-link to="/city" class="header-right">{{this.city}}<span class="iconfont arrow-icon">&#xe64a;</span></router-link>
  </div>
</template>

<script>
  import {
    mapState
  } from 'vuex'
  export default {
    name: 'HomeHeader',
    computed: {
      ...mapState(['city'])
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .header
    line-height: .86rem
    display flex 
    background-color $bgColor
    color #fff
    .header-left 
      height .63rem
      float left 
      .back-icon 
        text-align center
        font-size .4rem
    .header-input 
      flex 1
      background-color #fff
      border-radius .1rem
      height .64rem
      margin-top .12rem
      margin-left .2rem
      padding-left .2rem
      color #cccccc
      line-height .64rem
      .iconfont 
        margin-right .2rem
    .header-right 
      min-width 1.04rem
      padding 0 .1rem
      float right 
      text-align center
      color #fff
      .arrow-icon
        font-size .24rem
        margin-left .1rem
</style>

