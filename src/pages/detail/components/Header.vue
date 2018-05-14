<template>
  <div>
   <router-link v-show="showAbs" tag="div" to="/" :class="$style.header_abs">
     <i :class="['iconfont', 'icon-fanhui',$style.header_abs_back]"></i>
   </router-link>
   <div :class="$style.header_fixed" :style="opacityStyle" v-show="!showAbs">
     <router-link to="/">
      <div :class="$style.hederBack"><i :class="['iconfont', 'icon-fanhui']"></i></div>
    </router-link>
    景点详情
   </div>
  </div>
</template>

<script>

export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {opacity: 0}
    }
  },
  components: {
  },
  methods: {
    handelScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handelScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handelScroll)
  }
}
</script>

<style module>

  @value bgHeader from "styles/variables.css";

  .header_fixed {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    overflow: hidden;
    height: .86rem;
    line-height: .86rem;
    text-align: center;
    color: #fff;
    background-color: bgHeader;
    font-size: .32rem;
  }

  .hederBack {
    position: absolute;
    text-align: center;
    font-size: .40rem;
    width: .64rem;
    color: #fff;
  }

  .header_abs {
    position: absolute;
    left: .2rem;
    top: .2rem;
    width: .8rem;
    text-align: center;
    line-height: .8rem;
    border-radius: .4rem;
    background-color: rgba(0,0,0,.8);
  }

  .header_abs_back {
    color: #fff;
    font-size: .4rem;
  }
</style>
