<template>
  <header class="com-header">
    <div class="header-bar">
      <div class="header-content clearfix">
        <HeaderBarPosition />
        <HeaderBarNav />
      </div>
    </div>
    <div class="header-content clearfix">
      <HeaderTitleModule />
      <HeaderSearchModule />
    </div>
  </header>
</template>

<script>
import HeaderBarPosition from './header-bar-position'
import HeaderBarNav from './header-bar-nav'
import HeaderTitleModule from './header-title-module'
import HeaderSearchModule from './header-search-module'

export default {
  name: 'Header',
  components: {
    HeaderBarPosition,
    HeaderBarNav,
    HeaderTitleModule,
    HeaderSearchModule
  }
}
</script>

<style lang="scss" scoped>
@import "~assets/css/variables.scss";

.com-header {
  .header-bar {
    width: 100%;
    height: 40px;
    line-height: initial; // reset.css统一设置line-height: 1，此处需要重新设置
    background-color: $bg-color-base;
    color: $color-text-secondary;
    font-size: 12px;
  }
  .header-content {
    margin: 0 auto;
    padding-bottom: 35px;
    width: 1190px;
  }
}
</style>
