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
.com-header {
  .header-bar {
    width: 100%;
    height: 40px;
    background-color: #F8F8F8;
    font-size: 12px;
    color: #999;
  }
  .header-content {
    margin: 0 auto;
    padding-bottom: 35px;
    width: 1190px;
  }
}
</style>
