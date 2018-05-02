<template>
    <div :class="$style.list" ref="warpper">
      <div>
        <div :class="$style.area">
          <div :class="$style.title">当前城市</div>
          <div :class="$style.button_list">
            <div :class="$style.button_warpper">
              <div :class="$style.button">北京</div>
            </div>
          </div>
        </div>
        <div :class="$style.area">
          <div :class="$style.title">热门城市</div>
          <div :class="$style.button_list">
            <div
            :class="$style.button_warpper"
            v-for="item of hotCities"
            :key="item.id">
              <div :class="$style.button">{{item.name}}</div>
            </div>
          </div>
        </div>
        <div :class="$style.area"
        v-for="(item, key) of cities"
        :key="key"
        :ref="key">
          <div :class="$style.title">{{key}}</div>
          <div :class="$style.item_list">
            <div
            :class="$style.item"
            v-for="inneritem of item"
            :key="inneritem.id">
            {{inneritem.name}}
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>

import Bscroll from 'better-scroll'

export default {
  name: 'CityList',
  data () {
    return {
      scroll
    }
  },
  props: {
    hotCities: {
      type: Array
    },
    cities: {
      type: Object
    },
    letter: {
      type: String
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.warpper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const el = this.$refs[this.letter][0]
        this.scroll.scrollToElement(el)
      }
    }
  }
}
</script>

<style module>

  .list {
    position: absolute;
    overflow: hidden;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;
  }

  .title {
    line-height: .54rem;
    background-color: #eee;
    padding-left: .2rem;
    color: #666;
    font-size: .24rem;
    composes: border-bottom from 'styles/border.css';
  }

  .title::before, .title::after {
    background-color: #ccc;
  }

  .button_list {
    padding: .1rem .6rem .1rem .1rem;
    overflow: hidden;
  }

  .button_warpper {
    float: left;
    width: 33.33%;
  }

  .button {
    margin: .1rem;
    padding: .1rem 0;
    text-align: center;
    border: .02rem solid #ccc;
    border-radius: .06rem;
  }

  .item {
    line-height: .76rem;
    padding-left: .2rem;
    composes: border-bottom from 'styles/border.css';
  }

  .item::before, .item::after {
    background-color: #ccc;
  }
</style>
