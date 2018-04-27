<template>
  <swiper :options="swiperOption" :class="$style.wiper">
    <swiper-slide v-for="item of swiperList" :key="item.id">
        <img :class="$style.img"
        :src="item.imgUrl" alt="">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>
<script>

export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination',
          bulletActiveClass: this.$style.bullet
        },
        autoplay: true,
        loop: true
      },
      swiperList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/14/21f410d1016c8702.jpg_640x200_84d0effe.jpg'
      },
      {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/58/f55d3bc7fe9cd502.jpg_640x200_4153eac0.jpg'
      },
      {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/66/60ca5c5498293002.jpg_640x200_3224af33.jpg'
      }]
    }
  }
}
</script>

<style module>
    .wiper {
        width: 100%;
        height: 0; /* height31.25vw  */
        padding-bottom: 31.25%; /* 相对于宽度，实现图片自适应宽高比 */
        background-color: #f5f5f5;
    }

    .img {
        width: 100%;
    }

    .bullet {
      background-color: #fff;
      opacity: 1;
    }
</style>
