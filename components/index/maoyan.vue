<template>
  <div class="maoyan-container">
    <div style="background: linear-gradient(to right, rgb(250, 60, 104) 2%, rgb(254, 70, 77) 97%) rgb(250, 60, 104);" class="index-nav-container">
      <ul class="clearfix">
        <li class="title nav-item mf-shang-hei-regular">
          猫眼电影
        </li>
        <li class="nav-item active">
          即将上映
        </li>
        <li class="total nav-item">
          <nuxt-link to="/maoyan">
            <span>全部</span>
            <span class="right-arrow iconfont icon-btn_right" />
          </nuxt-link>
        </li>
      </ul>
    </div>
    <div class="scenes-body" />
  </div>
</template>

<script>
export default {
  name: 'Maoyan'
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.maoyan-container {
  position: relative;
  margin: 40px auto 0;
  .index-nav-container {
    box-sizing: border-box;
    width: 100%;
    height: 44px;
    line-height: 44px;
    font-size: 14px;
    color: $color-white;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
    .title {
      font-size: 18px;
      margin-left: 13px;
      margin-right: 10px;
    }
    .nav-item {
      position: relative;
      float: left;
      padding: 0 5px;
      cursor: pointer;
      text-transform: uppercase;
      &.active:after {
        content: " ";
        position: absolute;
        display: block;
        top: 37px;
        left: 0;
        right: 0;
        margin: auto;
        width: 2px;
        height: 0;
        border-left: 5px solid transparent;
        border-right: 5px solid transparent;
        border-bottom: 7px solid $color-white;
      }
    }
    .total {
      float: right;
      margin-right: 12px;
      a {
        color: $color-white;
      }
    }
    .right-arrow {
      display: inline-block;
      transform: scale(.8);
    }
  }
  .mf-shang-hei-regular {
    font-family: "MFShangHei-Regular" !important;
  }
}
</style>
