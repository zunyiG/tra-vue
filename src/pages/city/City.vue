<template>
    <div>
      <city-header></city-header>
      <city-Search></city-Search>
      <city-list></city-list>
      <city-alphabet></city-alphabet>
    </div>
</template>

<script>

import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'

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
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {
    getCityInfo () {
    },
    getCityInfoSucc ({data: {data: {city, swiperList, iconList, recommendList, weekendList} = {}, ret} = {}} = {}) {
      if (ret) {
        this.city = city
        this.swiperList = swiperList
        this.iconList = iconList
        this.recommendList = recommendList
        this.weekendList = weekendList
      }
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style>

</style>
