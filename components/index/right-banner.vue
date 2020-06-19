<template>
  <div class="right-banner">
    <div class="home-header-links">
      <nuxt-link v-for="item in linkList" :key="item.id" :to="item.path" :class="`${item.id}-link`">
        <span>{{ item.label }}</span>
      </nuxt-link>
    </div>
    <div class="banner-row clearfix">
      <div class="item banner-slider shadow">
        <BannerSlider />
      </div>
      <nuxt-link to="/xiuxianyule">
        <div class="item shadow pic-1" />
      </nuxt-link>
      <div class="item banner-logincard">
        <div>
          <div class="login-container" />
        </div>
      </div>
    </div>
    <div class="banner-row clearfix">
      <nuxt-link to="/hotel">
        <div class="item shadow pic-2" />
      </nuxt-link>
      <nuxt-link to="/jiaoyupeixun">
        <div class="item shadow pic-3" />
      </nuxt-link>
      <nuxt-link to="/">
        <div class="item shadow pic-4" />
      </nuxt-link>
      <div class="item download-app" />
    </div>
  </div>
</template>

<script>
import BannerSlider from './banner-slider'

export default {
  name: 'RightBanner',
  components: {
    BannerSlider
  },
  data () {
    return {
      linkList: [
        { id: 'waimai', label: '美团外卖', path: '/waimai' },
        { id: 'maoyan', label: '猫眼电影', path: '/maoyan' },
        { id: 'hotel', label: '美团酒店', path: '/hotel' },
        { id: 'homestay', label: '民宿／公寓', path: '/minsu' },
        { id: 'merchant', label: '商家入驻', path: '/' },
        { id: 'gongyi', label: '美团公益', path: '/gongyi' }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.right-banner {
  position: relative;
  float: left;
  margin-top: 10px;
  margin-left: 10px;
  .home-header-links {
    position: absolute;
    top: -45px;
    left: 20px;
    a {
      margin: 0 20px;
      color: $color-text-primary;
      font-size: 16px;
      font-weight: 700;
    }
    .waimai-link:hover {
      color: #FBC700;
    }
    .maoyan-link:hover {
      color: #ED1E24;
    }
    .hotel-link:hover {
      color: #F04D4E;
    }
    .homestay-link:hover {
      color: #FDC411;
    }
    .merchant-link:hover {
      color: #FE8C00;
    }
    .gongyi-link:hover {
      color: #F04D4E;
    }
  }
  .banner-row {
    .item {
      float: left;
    }
    .banner-slider {
      width: 550px;
      height: 240px;
      background: #ccc;
    }
    .pic-1 {
      margin: 0 10px;
      width: 150px;
      height: 240px;
      background: #ccc;
    }
    .pic-2, .pic-3 {
      margin-top: 10px;
      margin-right: 10px;
      width: 270px;
      height: 165px;
      background: #ccc;
    }
    .pic-4 {
      width: 150px;
      height: 165px;
      margin-top: 10px;
      margin-right: 10px;
      background: #ccc;
    }
    .download-app {
      margin-top: 10px;
      width: 228px;
      height: 165px;
      background: #fff;
      border: 1px solid $border-color-base;
    }
  }
  .shadow {
    transition: box-shadow .5s;
  }
  .shadow:hover {
    box-shadow: 0 5px 16px 0 rgab(0, 0, 0, .15);
    transition: box-shadow .5s;
  }
  .login-container {
    width: 228px;
    height: 238px;
    background: $color-white;
    border: 1px solid $border-color-base;
  }
}
</style>
