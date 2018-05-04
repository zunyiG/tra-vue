<template>
    <div :class="$style.header">
        <div :class="[$style.left, $style.hederBack]"><i :class="['iconfont', 'icon-fanhui']"></i></div>
        <div :class="$style.input">
            <i class="iconfont icon-sousuo"></i>
            输入城市/ 景点/ 主题
        </div>
        <router-link to="/city">
            <div :class="$style.right">{{this.doubleCity}}
                <i :class="['iconfont', 'icon-xiala', $style.headerCity]"></i>
            </div>
        </router-link>
    </div>
</template>

<script>

import { mapState, mapGetters } from 'vuex'
// import 'styles/variables.css'

export default {
  name: 'HomeHeader',
  computed: {
      ...mapState(['city']),
      ...mapGetters(['doubleCity'])
  }
}
</script>

<style module>

    @value bgHeader from "styles/variables.css";

    .d-flex {
        display: flex;
    }
    .header {
        composes: d-flex;
        line-height: .86rem;
        background-color: bgHeader;
        color: #fff;
    }

    .hederBack {
        text-align: center;
        font-size: .40rem;
    }

    .left {
        width: .64rem;
        float: left;
    }

    .headerCity {
        font-size: .24rem;
        margin-left: .05rem;
    }

    .input {
        flex: 1;
        height: .64rem;
        line-height: .64rem;
        margin-top: .12rem;
        margin-left: .2rem;
        padding-left: .2rem;
        border-radius: .05rem;
        background-color: #fff;
        color: #ccc;
    }

    .right {
        min-width: 1.04rem;
        padding: 0 .1rem;
        float: right;
        text-align: center;
        color:#fff;
    }

</style>
