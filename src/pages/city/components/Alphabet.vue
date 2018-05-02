<template>
  <ul :class="$style.list">
    <li :class="$style.item" v-for="(item, key) in cities" :key="key">{{key}}</li>
  </ul>
</template>

<script>

export default {
  name: 'CityAlphabet',
  props: {
    cities: {
      type: Object
    }
  }
}
</script>

<style module>

  @value bgHeader from "styles/variables.css";

  .list {
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    top: 1.58rem;
    right: 0;
    bottom: 0;
    width: .4rem;
  }

  .item {
    line-height: .4rem;
    text-align: center;
    color: bgHeader;
  }

</style>
