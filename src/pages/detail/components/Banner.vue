<template>
  <div>
    <div :class="$style.banner" @click="handleBannerClick">
      <img
      :src="bannerImg"
      :class="$style.banner_img">
      <div :class="$style.banner_info">
        <div :class="$style.banner_title">{{sightName}}</div>
        <div :class="$style.banner_number"><i :class="['iconfont','icon-tupian', $style.icon]"></i> 39</div>
      </div>
    </div>
    <fade-animation>
      <common-gallary
      :imgs="gallaryImgs"
      v-if="showGallary"
      :show="showGallary"
      @close="handleBannerClick"></common-gallary>
    </fade-animation>
  </div>
</template>

<script>

import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/Fade'

export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      showGallary: false
    }
  },
  components: {
    CommonGallary,
    FadeAnimation
  },
  methods: {
    handleBannerClick () {
      this.showGallary = !this.showGallary
    }
  }
}
</script>

<style module>

  .banner{
    position: relative;
    height: 0;
    padding-bottom: 55%;
    overflow: hidden;
    background-color: #f5f5f5;
  }

  .banner_info {
    display: flex;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: .6rem;
    color: #fff;
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8));
  }

  .banner_title {
    flex: 1;
    font-size: .32rem;
    padding: 0 .2rem;
  }

  .banner_number {
    line-height: .32rem;
    height: .32rem;
    padding: 0 .2rem;
    margin-top: .14rem;
    border-radius: .2rem;
    font-size: .24rem;
    background-color: rgba(0,0,0,.8);
  }

  .icon {
    font-size: .24rem;
  }

  .banner_img {
    width: 100%;
  }
</style>
