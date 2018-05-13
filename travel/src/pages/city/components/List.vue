<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
          <div class="item border-bottom">
            阿拉尔
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Bscroll from 'better-scroll'
  export default {
    name: 'CityList',
    mounted(){
      this.scroll = new Bscroll(this.$refs.wrapper)
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    position absolute
    left 0
    top 1.58rem
    right 0
    bottom 0
    overflow hidden
    .title
      line-height .54rem
      background-color #eeeeee
      padding-left .2rem
      color #666
      font-size .26rem
    .border-topbottom
      &:before
        border-color #cccccc
      &:after
        border-color #cccccc
    .border-bottom 
      &:before
        border-color #cccccc
    .button-list
      padding .1rem
      overflow hidden
      padding .1rem .6rem .1rem .1rem
      .button-wrapper
        width 33.33%
        float left
        .button
          text-align center
          margin .1rem
          border .02rem solid #ccc
          padding .1rem 0
          border-radius .06rem
    .item-list
      .item
        line-height .76rem
        color #666
        padding-left .2rem
</style>


