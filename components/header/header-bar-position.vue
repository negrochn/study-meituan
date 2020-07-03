<template>
  <div class="header-bar-position">
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
        <nuxt-link to="/">
          <span>立即登录</span>
        </nuxt-link>
      </div>
      <div class="extra-entry">
        <nuxt-link to="/">
          <span>注册</span>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeaderBarPosition'
}
</script>

<style lang="scss" scoped>
@import "~assets/css/variables.scss";

.header-bar-position {
  float: left;
  padding-top: 12px;
  .header-icon {
    font-size: 12px;
  }
  .current-city {
    color: $color-text-regular;
  }
  .change-city {
    margin: 0 4px;
    padding: 0 2px;
    background: $bg-color-reommend-card-hover;
    border: 1px solid $border-color-base;
    border-radius: 2px;
    color: $color-text-regular;
    // 由于设置了color，a的统一样式失效，需要重新设置a:hover
    &:hover {
      color: $color-link-hover;
    }
  }
  .near-citys {
    display: inline-block;
    .city-guess {
      margin: 0 4px;
    }
  }
  .user-entry {
    display: inline-block;
    margin-left: 15px;
    .user-up {
      display: inline;
      margin-left: 10px;
      a {
        color: $color-link-hover; // 立即登录特殊处理
      }
    }
    .extra-entry {
      display: inline;
      margin-left: 10px;
    }
  }
}
</style>
