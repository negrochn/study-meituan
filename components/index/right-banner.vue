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
        <div style="background-image: url(http://p0.meituan.net/codeman/e473bb428f070321269b23370ff02ba956209.jpg);" class="item shadow pic-1" />
      </nuxt-link>
      <div class="item banner-logincard">
        <div style="float: left;">
          <BannerLogin />
        </div>
      </div>
    </div>
    <div class="banner-row clearfix">
      <nuxt-link to="/hotel">
        <div style="background-image: url(http://p1.meituan.net/codeman/8cce56c467a17e04f3094d1e455462a0132772.png);" class="item shadow pic-2" />
      </nuxt-link>
      <nuxt-link to="/jiaoyupeixun">
        <div style="background-image: url(http://p1.meituan.net/codeman/16442c19da1f1c4544f794e29d99c92051716.jpg);" class="item shadow pic-3" />
      </nuxt-link>
      <nuxt-link to="/">
        <div style="background-image: url(http://p1.meituan.net/codeman/5b21cddb4bb1cbc3a9c3bce0f726c75940469.jpg);" class="item shadow pic-4" />
      </nuxt-link>
      <div class="item download-app">
        <div class="qrcode-box">
          <img src="//s1.meituan.net/bs/fe-web-meituan/60ac9a0/img/download-qr.png" alt="下载APP">
        </div>
        <p class="app-name">
          美团APP手机版
        </p>
        <p class="sl">
          <span class="red">1元起</span>
          <span class="gray">吃喝玩乐</span>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import BannerSlider from './banner-slider'
import BannerLogin from './banner-login'

export default {
  name: 'RightBanner',
  components: {
    BannerSlider,
    BannerLogin
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
      color: $color-link-waimai-hover;
    }
    .maoyan-link:hover {
      color: $color-link-maoyan-hover;
    }
    .hotel-link:hover {
      color: $color-link-hotel-hover;
    }
    .homestay-link:hover {
      color: $color-link-homestay-hover;
    }
    .merchant-link:hover {
      color: $color-link-merchant-hover;
    }
    .gongyi-link:hover {
      color: $color-link-gongyi-hover;
    }
  }
  .banner-row {
    .item {
      float: left;
    }
    .banner-slider {
      position: relative;
      width: 550px;
      height: 240px;
    }
    .pic-1 {
      margin: 0 10px;
      width: 150px;
      height: 240px;
      background-size: 150px;
      background-position: 50%;
      background-repeat: no-repeat;
      background-color: $bg-color-white;
    }
    .pic-2, .pic-3 {
      margin-top: 10px;
      margin-right: 10px;
      width: 270px;
      height: 165px;
      background-size: 270px;
      background-position: 50%;
      background-repeat: no-repeat;
    }
    .pic-4 {
      width: 150px;
      height: 165px;
      margin-top: 10px;
      margin-right: 10px;
      background-size: 150px;
      background-position: 50%;
      background-repeat: no-repeat;
      background-color: $bg-color-white;
    }
    .download-app {
      margin-top: 10px;
      width: 228px;
      height: 165px;
      background: $bg-color-white;
      border: 1px solid $border-color-base;
      .qrcode-box {
        margin: 10px auto 0;
        text-align: center;
        img {
          width: 95px;
          height: 95px;
        }
      }
      .app-name {
        font-size: 16px;
        color: $color-text-primary;
        font-weight: 500;
        text-align: center;
      }
      .sl {
        margin-top: 2px;
        font-size: 12px;
        font-weight: 500;
        text-align: center;
      }
      .red {
        margin-right: 5px;
        color: $color-text-red;
      }
      .gray {
        color: $color-text-gray;
      }
    }
  }
  .shadow {
    transition: box-shadow .5s;
  }
  .shadow:hover {
    box-shadow: 0 5px 16px 0 rgab(0, 0, 0, .15);
    transition: box-shadow .5s;
  }
}
</style>
