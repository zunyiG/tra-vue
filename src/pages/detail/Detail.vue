<template>
    <div>
      <detail-banner></detail-banner>
      <detail-header></detail-header>
      <div :class="$style.content"></div>
    </div>
</template>

<script>

import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'

export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader
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
