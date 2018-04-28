
<template>
  <swiper>
    <swiper-slide v-for="(iconpage, index) of pages" :key="'iconpage' + index">
      <div :class="$style.icons">
        <div :class="$style.icon" v-for="item of iconpage" :key="item.id">
          <div :class="$style.box">
            <img :class="$style.imgContent"
            :src="item.imgUrl" alt="">
          </div>
          <p :class="$style.directions">{{item.desc}}</p>
        </div>
      </div>
    </swiper-slide>
  </swiper>
</template>

<script>

export default {
  name: 'HomeIcons',
  props: {
    list: {
      type: Array
    }
  },
  data () {
    return {
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        pages[page] || (pages[page] = [])
        pages[page].push(item)
      })

      return pages
    }
  }
}
</script>

<style module>

    @value fontBaseColor from 'styles/variables.css';
    .icons {
      overflow: hidden;
      width: 100%;
      height: 0;
      padding-bottom: 50%; /* 自动撑开比例 2:1； 以父元素weidth 为参照 */
      margin-top: .1rem;
    }

    .icon {
      position: relative;
      float: left;
      width: 25%;
      padding-bottom: 25%;/* 以父元素weidth 为参照*/
      overflow: hidden;
    }

    .box {
      position: absolute;
      box-sizing: border-box;
      top: 0;
      left: 0;
      right: 0;
      bottom: .44rem;
      padding: .1rem;
    }

    .imgContent {
      height: 100%;
      display: block;
      margin: 0 auto;
    }

    .directions {
      position: absolute;
      text-align: center;
      bottom: 0;
      left: 0;
      right: 0;
      line-height: .44rem;
      composes: u_text_overflow_ellipsis from 'styles/utilities.css';
      color: fontBaseColor;
    }

</style>
