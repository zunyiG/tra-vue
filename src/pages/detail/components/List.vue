<template>
  <div>
    <div :class="$style.item" v-for="(item, index) of list" :key="'list'+index">
      <div :class="$style.title">
        <span :class="$style.item_icon"></span>
        {{item.title}}
      </div>
      <div :class="$style.children" v-if="item.children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style module>

  .title {
    line-height: .8rem;
    font-size: .32rem;
    padding: 0 .2rem;
    composes: border-bottom from 'styles/border.css';
  }

  .item_icon {
    display: inline-block;
    position: relative;
    width: .36rem;
    height: .36rem;
    top: .06rem;
    left: .2rem;
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
    margin-right: .1rem;
    background-size: .4rem 3rem;
  }

  .children {
    padding: 0 .2rem;
  }
</style>
