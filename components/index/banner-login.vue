<template>
  <div class="login-container">
    <div class="default">
      <div class="head-img-row">
        <img src="//s0.meituan.net/bs/fe-web-meituan/e350c4a/img/avatar.jpg" alt="">
      </div>
      <p class="user-name">
        Hi！你好
      </p>
      <nuxt-link to="/passport" class="btn-login">
        注册
      </nuxt-link>
      <nuxt-link to="/passport" class="btn-login">
        立即登录
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BannerLogin'
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.login-container {
  width: 228px;
  height: 238px;
  background: $color-white;
  border: 1px solid $border-color-base;
  .default {
    position: relative;
    padding-top: 30px;
    .head-img-row {
      margin: 0 auto 4px;
      text-align: center;
      border-radius: 30px;
      img {
        width: 47px;
        height: 47px;
        border-radius: 50%;
        border: 4px solid $border-color-base;
      }
    }
    .user-name {
      margin: 0 auto;
      width: 6em;
      color: $color-text-primary;
      font-size: 16px;
      font-weight: 500;
      text-align: center;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }
  }
  .btn-login {
    display: block;
    margin: 10px auto 15px;
    width: 118px;
    line-height: 38px;
    background: $color-white;
    border: 1px solid $border-color-base;
    border-radius: 40px;
    font-size: 14px;
    color: #333;
    text-align: center;
    transition: background-color .5s;
    &:hover {
      background-color: #f6f6f6;
      transition: background-color 0.5s;
    }
  }
}
</style>
