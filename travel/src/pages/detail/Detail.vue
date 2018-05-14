<template>
  <div>
    <banner-detail :sightName="sightName" :bannerImg="bannerImg" :bannerImgs="gallaryImgs"></banner-detail>
    <banner-header></banner-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'
  import BannerDetail from './components/Banner'
  import BannerHeader from './components/Header.vue'
  import DetailList from './components/List.vue'
  export default {
    name: 'Detail',
    data() {
      return {
        id: '',
        sightName: '',
        bannerImg: '',
        gallaryImgs: [],
        list: []
      }
    },
    beforeMount(id) {
      this.id = this.$route.params.id
      console.log(this.id)
    },
    methods: {
      getDetailInfo() {
        axios.get('/api/detail.json', {
          params: {
            id: this.id
          }
        }).then(this.handleGetDataSucc)
      },
      handleGetDataSucc(res) {
        res = res.data
        if (res.ret && res.data) {
          const data = res.data
          this.sightName = data.sightName
          this.bannerImg = data.bannerImg
          this.gallaryImgs = data.gallaryImgs
          this.list = data.categoryList
        }
      }
    },
    mounted() {
      this.getDetailInfo()
    },
    components: {
      BannerDetail,
      BannerHeader,
      DetailList
    }
  }
</script>

<style lang="stylus" scoped>
  .content 
    height 10rem
</style>


