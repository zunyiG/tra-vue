<template>
    <div>
      <detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
      <detail-header></detail-header>
      <div :class="$style.content">
        <detail-list :list="categoryList"></detail-list>
      </div>
    </div>
</template>

<script>

import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'

export default {
  name: 'Detail',
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      categoryList: []
    }
  },
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json?',{
        params: {
          id: this.$route.params.id
        }
      })
        .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc ({data: {data: {sightName, bannerImg, gallaryImgs, categoryList} = {}, ret} = {}} = {}) {
      this.sightName = sightName
      this.bannerImg = bannerImg
      this.gallaryImgs = gallaryImgs
      this.categoryList = categoryList
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style module>
  .content {
    height: 50rem;
  }
</style>
