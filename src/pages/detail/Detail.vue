<template>
  <div>
    <banner :sightName = "sightName" :bannerImg = "bannerImg"
    :bannerImgs = "gallaryImgs" />
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
import Axios from 'axios'
export default {
  components: {
    Banner,
    DetailHeader,
    DetailList
  },
  name: 'Detail',
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: []
    }
  },
  mounted () {
    this.getDetailInfo()
  },
  methods: {
    getDetailInfo () {
      Axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handelGetDataSucc)
    },
    handelGetDataSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.categoryList
      }
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
