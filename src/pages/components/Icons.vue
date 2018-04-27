
<template>
  <swiper>
    <swiper-slide v-for="(iconpage, index) of pages" :key="'iconpage' + index">
      <div :class="$style.icons">
        <div :class="$style.icon" v-for="item of iconpage" :key="item.id">
          <div :class="$style.box">
            <img :class="$style.imgContent"
            :src="item.imgUrl" alt="">
          </div>
          <p :class="$style.directions">{{item.desc}}</p>
        </div>
      </div>
    </swiper-slide>
  </swiper>
</template>

<script>

export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        'id': '0001',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        'desc': '景点门票'
      }, {
        'id': '0002',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1711/df/86cbcfc533330d02.png',
        'desc': '滑雪季'
      }, {
        'id': '0003',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1710/a6/83f636bd75ae6302.png',
        'desc': '泡温泉'
      }, {
        'id': '0004',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/35/2640cab202c41b02.png',
        'desc': '动植园'
      }, {
        'id': '0005',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/d0/e09575e66f4aa402.png',
        'desc': '游乐园'
      }, {
        'id': '0006',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/59/569d3c096e542502.png',
        'desc': '必游榜单'
      }, {
        'id': '0007',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/17/4bd370f3eb1acd02.png',
        'desc': '演出'
      }, {
        'id': '0008',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/7f/b1ea3c8c7fb6db02.png',
        'desc': '城市观光'
      }, {
        'id': '0009',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/a9/ffc620dbda9b9c02.png',
        'desc': '一日游'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        pages[page] || (pages[page] = [])
        pages[page].push(item)
      })

      return pages
    }
  }
}
</script>

<style module>

    @value fontBaseColor from 'styles/variables.css';
    .icons {
      overflow: hidden;
      width: 100%;
      height: 0;
      padding-bottom: 50%; /* 自动撑开比例 2:1； 以父元素weidth 为参照 */
      margin-top: .1rem;
    }

    .icon {
      position: relative;
      float: left;
      width: 25%;
      padding-bottom: 25%;/* 以父元素weidth 为参照*/
      overflow: hidden;
    }

    .box {
      position: absolute;
      box-sizing: border-box;
      top: 0;
      left: 0;
      right: 0;
      bottom: .44rem;
      padding: .1rem;
    }

    .imgContent {
      height: 100%;
      display: block;
      margin: 0 auto;
    }

    .directions {
      position: absolute;
      text-align: center;
      bottom: 0;
      left: 0;
      right: 0;
      line-height: .44rem;
      composes: u_text_overflow_ellipsis from 'styles/utilities.css';
      color: fontBaseColor;
    }

</style>
