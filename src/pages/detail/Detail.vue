<template>
    <div>
      <detail-banner></detail-banner>
      <detail-header></detail-header>
      <div :class="$style.content">
        <detail-list :list="list"></detail-list>
      </div>
    </div>
</template>

<script>

import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'

export default {
  name: 'Detail',
  data () {
    return {
      list: [{
        title: '成人票',
        children: [{
          title: '成人三馆联票'
        }, {
          title: '成人五馆联票',
          children: [{
            title: '成人五馆联票-1'
          }]
        }]
      }, {
        title: '学生票'
      }, {
        title: '儿童票'
      }, {
        title: '特惠票'
      }]
    }
  },
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  computed: {
  }
}
</script>

<style module>
  .content {
    height: 50rem;
  }
</style>
