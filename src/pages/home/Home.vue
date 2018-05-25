<template>
<div>
  <home-header :city="city"/>
  <home-swiper :list="swiperList"/>
  <home-icons :list="iconList"/>
  <home-recommend :list="recommendList"/>
  <home-Week :list="weekendList"/>
</div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeek from './components/Weekend'
import axios from 'axios'
export default{
  name: 'Home',
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeek
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      let backData = res.data
      if (backData.ret && backData.data) {
        const data = backData.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }

}
</script>

<style scoped>
</style>
