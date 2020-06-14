<template>
  <div class="position">
    <!-- 定位图标 -->
    <span class="header-icon icon-header_location" />
    <!-- 当前城市 -->
    <span class="current-city">杭州</span>
    <!-- 切换城市 -->
    <nuxt-link class="change-city" to="/changecity">
      <span>切换城市</span>
    </nuxt-link>
    <!-- 附近城市 -->
    <div class="near-citys">
      <span>[</span>
      <nuxt-link class="city-guess" to="/">
        <span>富阳</span>
      </nuxt-link>
      <nuxt-link class="city-guess" to="/">
        <span>德清</span>
      </nuxt-link>
      <nuxt-link class="city-guess" to="/">
        <span>临安</span>
      </nuxt-link>
      <span>]</span>
    </div>
    <!-- 用户信息 -->
    <div class="user-entry">
      <div class="user-up">
        <span>立即登录</span>
      </div>
      <div class="extra-entry">
        <span>注册</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.position {
  float: left;
  padding-top: 12px;
  .header-icon {
    font-size: 12px;
  }
  .current-city {
    font-size: 12px;
    color: #666;
  }
  .change-city {
    background: #F4F4F4;
    border: 1px solid #E5E5E5;
    border-radius: 2px;
    color: #666;
    margin: 0 4px;
    padding: 0 2px;
  }
  .near-citys {
    display: inline-block;
    .city-guess {
      margin: 0 4px;
      color: #999;
    }
  }
  .user-entry {
    display: inline-block;
    margin-left: 15px;
    .user-up {
      display: inline;
      margin-left: 10px;
      color: #FE8C00;
    }
    .extra-entry {
      display: inline;
      margin-left: 10px;
    }
  }
}
</style>
