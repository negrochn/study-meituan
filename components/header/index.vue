<template>
  <header class="com-header">
    <div class="header-bar">
      <div class="header-content clearfix">
        <Position />
        <Nav />
      </div>
    </div>
  </header>
</template>

<script>
import Position from './position'
import Nav from './nav'

export default {
  name: 'Header',
  components: {
    Position,
    Nav
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
