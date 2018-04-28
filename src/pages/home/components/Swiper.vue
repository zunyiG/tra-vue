<template>
  <swiper :options="swiperOption" :class="$style.wiper">
    <swiper-slide v-for="item of list" :key="item.id">
        <img :class="$style.img"
        :src="item.imgUrl" alt="">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>
<script>

export default {
  name: 'HomeSwiper',
  props: {
    list: {
      type: Array
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination',
          bulletActiveClass: this.$style.bullet
        },
        autoplay: true,
        loop: true
      }
    }
  },
  mounted () {
    // console.log(this.list);
    // 子组件会在父组件渲染前进行渲染， 直到父组件渲染完成后才会把值传入子组件， 所以子组件渲染完成后值为空
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
