<template>
    <div>
      <home-header></home-header>
    </div>
</template>

<script>

import HomeHeader from './components/Header'

export default {
  name: 'Home',
  components: {
    HomeHeader
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
    getHomeInfo () {
    },
    getHomeInfoSucc ({data: {data: {city, swiperList, iconList, recommendList, weekendList} = {}, ret} = {}} = {}) {
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
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
