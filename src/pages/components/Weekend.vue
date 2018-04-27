<template>
    <div>
      <div :class="$style.title">周末去哪儿</div>
      <ul>
        <li v-for="item of recommendList" :key="item.id">
          <div :class="$style.item_img_warpper">
            <img :src="item.imgUrl" alt="" 
            :class="$style.item_img">
          </div>
          <div :class="$style.item_info">
            <p :class="$style.item_title">{{item.title}}</p>
            <p :class="$style.item_dsc">{{item.dsc}}</p>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>

export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1507/e8/7afdd7b86bf778.jpg_r_640x214_c70adb31.jpg',
        title: '慢游成都最美古镇',
        dsc: '撷取一份悠闲，寻觅散落在时光里的幸福'
      },{
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1507/e8/7afdd7b86bf778.jpg_r_640x214_c70adb31.jpg',
        title: '慢游成都最美古镇',
        dsc: '撷取一份悠闲，寻觅散落在时光里的幸福'
      },{
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1507/e8/7afdd7b86bf778.jpg_r_640x214_c70adb31.jpg',
        title: '慢游成都最美古镇',
        dsc: '撷取一份悠闲，寻觅散落在时光里的幸福'
      }]
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

.item_img_warpper {
    overflow: hidden;
    height: 0;
    padding-bottom: 33.9%;
  }

  .item_img {
    width: 100%;
  }

  .item_info {
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

</style>
