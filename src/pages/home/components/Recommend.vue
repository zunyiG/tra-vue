<template>
    <div>
      <div :class="$style.title">热门推荐</div>
      <ul>
        <li :class="$style.item" v-for="item of list" :key="item.id">
          <img :src="item.imgUrl" :class="$style.item_img">
          <div :class="$style.item_info">
            <p :class="$style.item_title">{{item.title}}</p>
            <p :class="$style.item_dsc">{{item.desc}}</p>
            <button :class="$style.item_btn">查看详情</button>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>

export default {
  name: 'HomeRecommend',
  props: {
    list: {
      type: Array
    }
  },
  data () {
    return {
    }
  }
}
</script>

<style module>

  .title {
    margin-top: .2rem;
    line-height: .8rem;
    background-color: #eee;
    text-indent: .2rem;
  }

  .item {
    overflow: hidden;
    display: flex;
    height: 1.9rem;
    composes: border-bottom from 'styles/border.css';
  }

  .item_img {
    height: 1.7rem;
    width: 1.7rem;
    margin: .1rem;
  }

  .item_info {
    flex: 1;
    min-width: 0;
    padding: .1rem;
  }

  .item_title {
    line-height: .54rem;
    font-size: .32rem;
  }

  .item_dsc {
    line-height: .4rem;
    color: #aaa;
    composes: u_text_overflow_ellipsis from 'styles/utilities.css';
  }

  .item_btn {
    margin-top: .16rem;
    line-height: .44rem;
    padding: 0 .1rem;
    border-radius: .06rem;
    background-color: #ff9300;
    color: #fff;
  }
</style>
