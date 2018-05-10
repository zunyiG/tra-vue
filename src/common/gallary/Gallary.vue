<template>
    <div :class="$style.container" @click="handleGallaryClick" v-show="show">
      <div :class="$style.warpper">
        <swiper :options="swiperOption">
          <swiper-slide v-for="(item, index) of imgs" :key="'img'+index">
              <img :class="$style.img"
              :src="item" alt="">
          </swiper-slide>
          <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
      </div>
    </div>
</template>

<script>

export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    },
    show: Boolean
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination',
          type: 'fraction',
          observeParents: true,
          observer: true
        }
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style module>

  :global(.swiper-pagination-fraction) {
    color: #fff;
    bottom: -1rem;
  }

  :global(.swiper-container) {
    overflow: inherit;
  }

  .container {
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: fixed;
    z-index: 99;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    background-color: #000;
  }

  .warpper {
    width: 100%;
    height: 0;
    padding-bottom: 100%;
  }

  .img {
    width: 100%;
  }

</style>
