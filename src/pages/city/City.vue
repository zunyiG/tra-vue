<template>
    <div>
      <city-header></city-header>
      <city-Search></city-Search>
      <city-list :cities="cities" :hotCities="hotCities"></city-list>
      <city-alphabet :cities="cities"></city-alphabet>
    </div>
</template>

<script>

import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'

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
      cities: {},
      hotCities: []
    }
  },
  methods: {
    getCityList () {
      axios.get('/api/city.json')
        .then(this.getCityListSucc)
    },
    getCityListSucc ({data: {data: {city, hotCities, cities} = {}, ret} = {}} = {}) {
      if (ret) {
        this.city = city
        this.cities = cities
        this.hotCities = hotCities
      }
    }
  },
  mounted () {
    this.getCityList()
  }
}
</script>

<style>

</style>
