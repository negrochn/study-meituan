<template>
  <nav class="nav">
    <ul class="nav-ul">
      <li class="has-child" @mouseenter="isUserInfoShow = true" @mouseleave="isUserInfoShow = false">
        <nuxt-link to="/account/userinfo">
          我的美团
        </nuxt-link>
        <ul v-show="isUserInfoShow" class="header-nav-second">
          <li>
            <nuxt-link to="/orders">
              我的订单
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/collections">
              我的收藏
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/vouchers">
              抵用券
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/account/settings">
              账户设置
            </nuxt-link>
          </li>
        </ul>
      </li>
      <li>
        <nuxt-link to="/mobile/down/meituan">
          手机APP
        </nuxt-link>
      </li>
      <li class="has-child" @mouseenter="isBusinessCenterShow = true" @mouseleave="isBusinessCenterShow = false">
        <span>商家中心</span>
        <ul v-show="isBusinessCenterShow" class="header-nav-merchant header-nav-second">
          <li>
            <nuxt-link to="/canyin/PC">
              美团餐饮商户中心
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/">
              登录商家中心
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/shouyin">
              美团智能收银
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/emis/settle/merchantsSettle">
              我想合作
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/mobile">
              手机免费开店
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/daili">
              餐饮代理商招募
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/">
              商家申请开票
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/paidui">
              免费合作美团排队
            </nuxt-link>
          </li>
        </ul>
      </li>
      <li class="has-child" @mouseenter="isMeituanRulesShow = true" @mouseleave="isMeituanRulesShow = false">
        <span>美团规则</span>
        <ul v-show="isMeituanRulesShow" class="header-nav-second">
          <li>
            <nuxt-link to="/rules-center">
              规则中心
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/rules-center/rules">
              规则目录
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/rules-center/advices">
              规则评议院
            </nuxt-link>
          </li>
        </ul>
      </li>
      <li class="has-child">
        <span>网站导航</span>
        <div class="header-nav-site header-nav-second">
          <dl class="header-jiulv header-nav-third">
            1
          </dl>
          <dl class="header-meishi header-nav-third">
            2
          </dl>
          <dl class="header-movie header-nav-third">
            3
          </dl>
          <dl class="header-app header-nav-third">
            4
          </dl>
        </div>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Nav',
  data () {
    return {
      isUserInfoShow: false,
      isBusinessCenterShow: false,
      isMeituanRulesShow: false
    }
  }
}
</script>

<style lang="scss" scoped>
.nav {
  float: right;
  .nav-ul {
    margin: 0;
    padding: 0;
    & > li {
      float: left;
      position: relative;
      height: 40px;
      padding: 12px 14px;
      box-sizing: border-box;
      border-left: 1px solid transparent;
      border-right: 1px solid transparent;
      list-style: none;
      & > a, & > span {
        color: #999;
        &:hover {
          color: #FE8C00;
        }
      }
      .header-nav-second {
        box-sizing: content-box;
        position: absolute;
        right: -1px;
        top: 95%;
        margin: 0;
        padding: 0;
        width: 100%;
        background: #fff;
        border: 1px solid #E5E5E5;
        box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
        border-bottom-left-radius: 4px;
        border-bottom-right-radius: 4px;
        z-index: 1000;
        &:after {
          content: "";
          background: #fff;
          width: 76px;
          height: 3px;
          position: absolute;
          top: -2px;
          right: 0;
        }
        li {
          margin: 0;
          padding: 0;
          text-align: center;
          list-style: none;
          a {
            display: block;
            line-height: 35px;
            color: #999;
            &:hover {
              color: #FE8C00;
            }
          }
        }
        .header-nav-third {
          float: left;
          margin-right: 47px;
        }
      }
      .header-nav-merchant {
        width: 140%;
        border-top-left-radius: 4px;
      }
      .header-nav-site {
        width: 1200px;
        box-sizing: border-box;
        border-top-left-radius: 4px;
        padding: 30px 36px 36px 47px;
        .header-jiulv {
          width: 234px;
        }
        .header-meishi {
          width: 156px;
        }
        .header-movie {
          width: 90px;
        }
        .header-app {
          float: right;
        }
      }
    }
    & > .has-child {
      &:hover {
        background-color: #fff;
        border-color: #E5E5E5;
        box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      }
    }
  }
}
</style>
