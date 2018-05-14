<template>
  <div>
    <div :class="$style.banner" @click="handleBannerClick">
      <img
      src="//img1.qunarzz.com/sight/p0/1612/1d/1d9a740c1f9e0efaa3.img.jpg_600x330_3b0fdac5.jpg"
      :class="$style.banner_img">
      <div :class="$style.banner_info">
        <div :class="$style.banner_title">成都海昌极地海洋公园(AAAA景区)</div>
        <div :class="$style.banner_number"><i :class="['iconfont','icon-tupian', $style.icon]"></i> 39</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" :show="showGallary" @close="handleBannerClick"></common-gallary>
  </div>
</template>

<script>

import CommonGallary from 'common/gallary/Gallary'

export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['//img1.qunarzz.com/sight/p0/1705/ed/edd4063a442f30c1a3.img.jpg_600x330_4e335e78.jpg',
        '//img1.qunarzz.com/sight/p0/1705/ed/edd4063a442f30c1a3.img.jpg_600x330_4e335e78.jpg']
    }
  },
  components: {
    CommonGallary
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
