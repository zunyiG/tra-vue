<template>
    <div :class="$style.header"> 
      <router-link to="/">
        <div :class="$style.hederBack"><i :class="['iconfont', 'icon-fanhui']"></i></div>
      </router-link>
      城市选择
    </div>
</template>

<script>

export default {
  name: 'CityHeader'
}
</script>

<style module>

  @value bgHeader from "styles/variables.css";

  .header {
    position: relative;
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

</style>
