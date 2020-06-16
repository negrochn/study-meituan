<template>
  <div class="index-container">
    <div class="banner-container clearfix">
      <div class="left-banner">
        <div class="category-nav-container">
          <div class="category-nav-title-wrapper">
            <span class="category-nav-title">全部分类</span>
            <span class="title-icon" />
          </div>
          <div class="category-nav-content-wrapper">
            <ul>
              <li class="nav-li" />
            </ul>
          </div>
          <div class="category-nav-detail-wrapper" />
        </div>
      </div>
      <div class="right-banner" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Banner'
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.banner-container {
  .left-banner {
    float: left;
    .category-nav-container {
      position: relative;
      float: left;
      box-sizing: border-box;
      margin-top: -50px;
      width: 230px;
      height: 475px;
      background: $color-white;
      color: $color-text-regular - $color-text-span2;
      border: 1px solid $border-color-base;
      .category-nav-title-wrapper {
        box-sizing: border-box;
        padding-top: 15px;
        height: 50px;
        .category-nav-title {
          margin-left: 15px;
          color: $color-text-primary;
          font-size: 16px;
          font-weight: 700;
        }
      }
    }
  }
  .right-banner {
    float: right;
  }
}
</style>
