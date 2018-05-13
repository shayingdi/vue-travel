<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item in RecommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'HomeWeekend',
    data() {
      return {
        RecommendList: [{
            id: '0001',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1505/bc/83feb2e003d0dd.jpg_r_640x214_0b7269b8.jpg',
            title: '杭州必游TOP10',
            desc: '杭州必游TOP10杭州必游TOP10杭州必游TOP10杭州必游TOP10杭州必游TOP10'
          },
          {
            id: '0002',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1505/bc/83feb2e003d0dd.jpg_r_640x214_0b7269b8.jpg',
            title: '杭州必游TOP10',
            desc: '杭州必游TOP10杭州必游TOP10杭州必游TOP10杭州必游TOP10杭州必游TOP10'
          },
          {
            id: '0003',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1505/bc/83feb2e003d0dd.jpg_r_640x214_0b7269b8.jpg',
            title: '杭州必游TOP10',
            desc: '杭州必游TOP10杭州必游TOP10杭州必游TOP10杭州必游TOP10杭州必游TOP10'
          }
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height .8rem
    background-color #eee
    text-indent .2rem
    margin-top .2rem
  .item
    overflow hidden
    .item-img-wrapper
      width 100%
      height 0
      overflow hidden
      padding-bottom 33.9%
      .item-img
        width 100%
    .item-info
      padding .1rem
      min-width 0
      .item-title
        font-size .32rem
        line-height .54rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #616161
        ellipsis()
      .item-button
        background-color #ff9300
        padding 0 .2rem
        border-radius .06rem
        margin-top .16rem 
        color #fff
        line-height .44rem
</style>


