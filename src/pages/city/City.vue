<template>
  <div>
    <city-header/>
    <city-search :cities="cities"/>
    <city-list :cities="cities" :hot = "hotCities" :letter= "letter"/>
    <CityAlphabet :cities="cities" @change = "handleLetter"/>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components//Alphabet'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    getInfoCity () {
      axios.get('/api/city.json').then(this.handlegetCityInfoSucc)
    },
    handlegetCityInfoSucc (data) {
      let res = data.data
      if (res.ret && res.data) {
        this.cities = res.data.cities
        this.hotCities = res.data.hotCities
      }
    },
    handleLetter (data) {
      this.letter = data
    }
  },
  mounted () {
    this.getInfoCity()
  }
}
</script>

<style lang="scss" scoped>

</style>
