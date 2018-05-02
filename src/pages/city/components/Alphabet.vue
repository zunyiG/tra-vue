<template>
  <ul :class="$style.list">
    <li
    :class="$style.item"
    v-for="(item, key)
    in cities"
    :key="key"
    :ref="key"
    @touchstart="handleTouchStart"
    @touchmove="handleTouchMove"
    @touchend="handleTouchEnd"
    @click="handleLetterClick">{{key}}</li>
  </ul>
</template>

<script>

export default {
  name: 'CityAlphabet',
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timmer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  props: {
    cities: {
      type: Object
    }
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timmer) {
          clearTimeout(this.timmer)
        }
        this.timmer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - this.startY) / 20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
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
