<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item in hot" :key="item.id" @click="handleBtnClick(item.name)">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) in cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom" v-for="innerItem in item" :key="innerItem.id" @click="handleBtnClick(innerItem.name)">
            {{innerItem.name}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Bscroll from 'better-scroll'
  import {
    mapState,
    mapMutations
  } from 'vuex'
  export default {
    name: 'CityList',
    props: {
      cities: Object,
      hot: Array,
      letter: String
    },
    computed: {
      ...mapState(['city'])
    },
    methods: {
      handleBtnClick(city) {
        //this.$store.dispatch('changeCity', city)
        this.changeCity(city)
        this.$router.push('/')
      },
      ...mapMutations(['changeCity'])
    },
    watch: {
      letter() {
        if (this.letter) {
          const element = this.$refs[this.letter][0]
          this.scroll.scrollToElement(element)
        }
      }
    },
    mounted() {
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


