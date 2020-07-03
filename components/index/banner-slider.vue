<template>
  <div class="slider">
    <div class="slider-content clearfix">
      <div v-for="(item, index) in sliderList" :key="item.path" :style="curIndex === index ? 'opacity: 1; z-index: 50;' : ''" class="slider-item">
        <nuxt-link :to="item.path">
          <div :style="`background-image: url(${item.url});`" class="slider-img-div" />
        </nuxt-link>
      </div>
    </div>
    <div class="slider-pagination">
      <div v-for="(item, index) in sliderList" :key="item.path" :style="curIndex === index ? 'opacity: .9;' : ''" class="pagination" />
    </div>
    <div class="btn btn-next" @click="onNextClick">
      <i class="iconfont icon-btn_right" />
    </div>
    <div class="btn btn-pre" @click="onPreClick">
      <i class="iconfont icon-btn_left" />
    </div>
  </div>
</template>

<script>
import _ from 'lodash'

export default {
  name: 'BannerSlider',
  data () {
    return {
      sliderList: [
        {
          url: 'http://p0.meituan.net/codeman/daa73310c9e57454dc97f0146640fd9f69772.jpg',
          path: '/hotel'
        },
        {
          url: 'http://p1.meituan.net/codeman/826a5ed09dab49af658c34624d75491861404.jpg',
          path: '/meishi'
        },
        {
          url: 'http://p0.meituan.net/codeman/a97baf515235f4c5a2b1323a741e577185048.jpg',
          path: '/waimai'
        },
        {
          url: 'http://p0.meituan.net/codeman/33ff80dc00f832d697f3e20fc030799560495.jpg',
          path: '/maoyan'
        },
        {
          url: 'https://p1.meituan.net/travelcube/01d2ab1efac6e2b7adcfcdf57b8cb5481085686.png',
          path: '/paidui'
        }
      ],
      curIndex: 0,
      timer: null
    }
  },
  mounted () {
    _.delay(this.slide, 5000)
  },
  methods: {
    slide (step = 1) {
      clearTimeout(this.timer)
      const length = this.sliderList.length
      // 通过 + length 的方式，防止 curIndex 出现负数
      this.curIndex = (this.curIndex + step + length) % length
      this.timer = _.delay(this.slide, 5000)
    },
    onNextClick () {
      this.slide()
    },
    onPreClick () {
      this.slide(-1)
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.slider {
  width: 100%;
  height: 100%;
  .slider-content {
    height: 100%;
    .slider-item {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      opacity: 0;
      z-index: 9;
    }
  }
  .slider-img-div {
    display: inline-block;
    width: 100%;
    height: 100%;
    background-repeat: no-repeat;
    background-position: 50%;
    background-size: cover;
  }
  .slider-pagination {
    position: absolute;
    left: 50%;
    bottom: 10px;
    z-index: 99;
    transform: translate(-50%);
    .pagination {
      float: left;
      margin-right: 10px;
      width: 10px;
      height: 2px;
      background: $bg-color-white;
      opacity: .2;
      transition: opacity .5s;
      &:last-child {
        margin-right: 0;
      }
    }
  }
  .btn {
    position: absolute;
    top: 43%;
    width: 40px;
    height: 40px;
    background: #333;
    text-align: center;
    border-radius: 20px;
    transform: scale(.95);
    opacity: 0;
    transition: opacity .5s;
    z-index: 99;
    cursor: pointer;
    .iconfont {
      line-height: 40px;
      color: $color-text-white;
      font-size: 20px;
      text-align: center;
    }
  }
  .btn-next {
    right: 10px;
  }
  .btn-pre {
    left: 10px;
  }
  &:hover {
    .btn {
      opacity: .8;
      transition: opacity .5s;
    }
  }
}
</style>
