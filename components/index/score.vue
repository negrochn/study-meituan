<template>
  <div class="score">
    <div class="rate-stars">
      <ul class="rate-stars-ul rate-stars-dark">
        <li><i class="iconfont icon-star_icon" /></li>
        <li><i class="iconfont icon-star_icon" /></li>
        <li><i class="iconfont icon-star_icon" /></li>
        <li><i class="iconfont icon-star_icon" /></li>
        <li><i class="iconfont icon-star_icon" /></li>
      </ul>
      <ul :style="lightWidth" class="rate-stars-ul rate-stars-light">
        <li><i class="iconfont icon-star_icon" /></li>
        <li><i class="iconfont icon-star_icon" /></li>
        <li><i class="iconfont icon-star_icon" /></li>
        <li><i class="iconfont icon-star_icon" /></li>
        <li><i class="iconfont icon-star_icon" /></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Score',
  props: {
    score: {
      type: String || Number,
      default: 0
    }
  },
  computed: {
    lightWidth () {
      return `width: ${this.score / 5 * 100}%;`
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.score {
  .rate-stars {
    position: relative;
    display: inline-block;
    width: 84px;
    height: 24px;
    .rate-stars-ul {
      margin: 3px 0;
      padding: 0;
      text-align: left;
      white-space: nowrap;
      &>li {
        display: inline-block;
        padding: 0 2px;
      }
    }
    .rate-stars-dark {
      color: $color-rate-star-dark;
    }
    .rate-stars-light {
      position: absolute;
      top: 0;
      color: $color-rate-star-light;
      overflow: hidden;
    }
  }
}
</style>
