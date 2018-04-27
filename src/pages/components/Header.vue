<template>
    <div :class="$style.header">
        <div :class="[$style.left, $style.hederBack]"><i :class="['iconfont', 'icon-fanhui']"></i></div>
        <div :class="$style.input">
            <i class="iconfont icon-sousuo"></i>
            输入城市/ 景点/ 主题
        </div>
        <div :class="$style.right">城市<i :class="['iconfont', 'icon-xiala', $style.headerCity]"></i></div>
    </div>
</template>

<script>

// import 'styles/variables.css'

export default {
  name: 'HomeHeader'
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

    .headerCity {
        font-size: .24rem;
        margin-left: .05rem;
    }

    .left {
        width: .64rem;
        float: left;
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
        widows: 1.24rem;
        padding: 0 .24rem;
        float: right;
        text-align: center;
    }

</style>
