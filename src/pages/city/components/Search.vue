
<template>
    <div>
      <div :class="$style.search" >
        <input :class="$style.search_input" v-model="keyword"  type="text" placeholder="输入城市名或拼音"/>
      </div>
      <div :class="$style.search_content" ref="search" v-show="keyword">
        <ul>
          <li
           :class="$style.search_item"
           v-for="item of list"
           :key="item.id"
            @click="handelCityClick(item.name)"
            >{{item.name}}</li>
          <li :class="$style.search_item" v-show="hasData">没有找到匹配数据</li>
        </ul>
      </div>
    </div>
</template>

<script>

import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'

export default {
  name: 'CitySearch',
  props: {
    citys: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null,
      hasData: false
    }
  },
  methods: {
    handelCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const res = []
        for (let key in this.citys) {
          this.citys[key].forEach(value => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              res.push(value)
            }
          })
        }
        this.list = res
        this.hasData = !res.length
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>

<style module>

  @value bgHeader from "styles/variables.css";

  .search {
    height: .72rem;
    padding: 0 .1rem;
    background: bgHeader;
  }

  .search_content {
    position: absolute;
    overflow: hidden;
    z-index: 1;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #eee;
  }

  .search_input {
    box-sizing: border-box;
    width: 100%;
    height: .62rem;
    padding: 0 .1rem;
    line-height: .62rem;
    text-align: center;
    border-radius: .06rem;
    color: #666;
  }

  .search_item {
    line-height: .62rem;
    padding-left: .2rem;
    color: #666;
    background-color: #fff;
    composes: border-bottom from 'styles/border.css';
  }

</style>
