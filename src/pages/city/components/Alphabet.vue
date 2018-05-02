<template>
  <ul :class="$style.list">
    <li :class="$style.item">A</li>
    <li :class="$style.item">B</li>
    <li :class="$style.item">C</li>
    <li :class="$style.item">D</li>
    <li :class="$style.item">E</li>
    <li :class="$style.item">F</li>
  </ul> 
</template>

<script>

export default {
  name: 'CityAlphabet'
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
