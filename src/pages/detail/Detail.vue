<template>
  <div>
    <banner/>
    <detail-header/>
    <div class="content">
      <detail-list :list = "list"/>
    </div>
  </div>
</template>

<script>
import Banner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  components: {
    Banner,
    DetailHeader,
    DetailList
  },
  name: 'Detail',
  data () {
    return {
      list: [{
        title: '成人票',
        children: [{
          title: '成人三馆连票',
          children: [{
            title: '成人三馆连票-某一连锁店销售'
          }]
        }, {
          title: '成人五管连票'
        }]
      }, {
        title: '学生票'
      }, {
        title: '儿童票'
      }, {
        title: '特惠票'
      }]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/base.scss';
@import '~styles/varibles.scss';
.content {
  @include x-rem(height, 50)
}
</style>
