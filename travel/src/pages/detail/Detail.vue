<template>
  <div>
    <banner-detail></banner-detail>
    <banner-header></banner-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
  import BannerDetail from './components/Banner'
  import BannerHeader from './components/Header.vue'
  import DetailList from './components/List.vue'
  export default {
    name: 'Detail',
    data() {
      return {
        list: [{
            title: '学生票',
            children: [{
              title: '成人联票1'
            }, {
              title: '成人联票2'
            }]
          },
          {
            title: '儿童票'
          }
        ]
      }
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
    height 50rem
</style>


