<template>
    <div>
      <city-header></city-header>
      <city-Search :citys="cities"></city-Search>
      <city-list
      :cities="cities"
      :hotCities="hotCities"
      :letter="letter"></city-list>
      <city-alphabet
      :cities="cities"
      @change="handleLetterChange"></city-alphabet>
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
      hotCities: [],
      letter: ''
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
    },
    handleLetterChange (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityList()
  }
}
</script>

<style>

</style>
