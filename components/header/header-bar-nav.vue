<template>
  <nav class="header-bar-nav">
    <ul class="header-nav-first">
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
      <li class="has-child" @mouseenter="isSiteShow = true" @mouseleave="isSiteShow = false">
        <span>网站导航</span>
        <div v-show="isSiteShow" class="header-nav-site header-nav-second">
          <dl
            v-for="item in siteList"
            :key="item.id"
            :class="`header-${item.id} header-nav-third`"
          >
            <dt>{{ item.label }}</dt>
            <dd v-for="itm in item.children" :key="itm.label">
              <nuxt-link :to="itm.path">
                <img v-if="itm.imgSrc" class="appicon" :src="itm.imgSrc" :alt="itm.label">
                <span v-else>{{ itm.label }}</span>
              </nuxt-link>
            </dd>
          </dl>
        </div>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'HeaderBarNav',
  data () {
    return {
      isUserInfoShow: false,
      isBusinessCenterShow: false,
      isMeituanRulesShow: false,
      isSiteShow: false,
      siteList: [
        {
          id: 'jiulv',
          label: '酒店旅游',
          children: [
            { label: '国际机票', path: '/iflight' },
            { label: '火车票', path: '/train' },
            { label: '民宿', path: '/minsu' },
            { label: '经济型酒店', path: '/hotel/hangzhou/c20036' },
            { label: '主题酒店', path: '/hotel/hangzhou/c20037' },
            { label: '商务酒店', path: '/hotel/hangzhou/c20038' },
            { label: '公寓', path: '/hotel/hangzhou/c20039' },
            { label: '豪华酒店', path: '/hotel/hangzhou/c20040' },
            { label: '客栈', path: '/hotel/hangzhou/c20041' },
            { label: '青年旅社', path: '/hotel/hangzhou/c20042' },
            { label: '度假酒店', path: '/hotel/hangzhou/c20043' },
            { label: '别墅', path: '/hotel/hangzhou/c20044' },
            { label: '农家院', path: '/hotel/hangzhou/c20045' }
          ]
        },
        {
          id: 'meishi',
          label: '吃美食',
          children: [
            { label: '烤鱼', path: '/meishi/c20004' },
            { label: '特色小吃', path: '/meishi/c36' },
            { label: '烧烤', path: '/meishi/c54' },
            { label: '自助餐', path: '/meishi/c40' },
            { label: '火锅', path: '/meishi/c17' },
            { label: '代金券', path: '/meishi/c393' }
          ]
        },
        {
          id: 'movie',
          label: '看电影',
          children: [
            { label: '热映电影', path: '/maoyan/films' },
            { label: '热门影院', path: '/maoyan/cinemas' },
            { label: '热映电影口碑榜', path: '/maoyan/board' },
            { label: '最受期待电影', path: '/maoyan/board/6' },
            { label: '国内票房榜', path: '/maoyan/board/1' },
            { label: '北美票房榜', path: '/maoyan/board/2' },
            { label: '电影排行榜', path: '/maoyan/board/4' }
          ]
        },
        {
          id: 'app',
          label: '手机应用',
          children: [
            { label: '美团app', path: '/mobile/down/meituan', imgSrc: '//s0.meituan.net/bs/fe-web-meituan/2d53095/img/appicons/meituan.png' },
            { label: '外卖app', path: '/mobile/down/download/default', imgSrc: '//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/waimai.png' },
            { label: '民宿app', path: '/minsu/app', imgSrc: 'https://p0.meituan.net/travelcube/162c3308d9622f6d9cfaa49e60be4dca8573.png' },
            { label: '点评app', path: '/dianping', imgSrc: '//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/dianping.png' },
            { label: '猫眼app', path: '/maoyan/app', imgSrc: '//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/maoyan.png' }
          ]
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.header-bar-nav {
  float: right;
  .header-nav-first {
    margin: 0;
    padding: 0;
    a {
      color: #999;
        &:hover {
          color: #FE8C00;
        }
    }
    & > li {
      float: left;
      position: relative;
      height: 40px;
      padding: 12px 14px;
      box-sizing: border-box;
      border-left: 1px solid transparent;
      border-right: 1px solid transparent;
      list-style: none;
      & > span {
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
        text-align: center;
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
          dt {
            margin-bottom: 26px;
            color: #222;
            font-size: 14px;
            font-weight: 500;
          }
          dd {
            a {
              display: block;
              padding: 5px 0;
            }
          }
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
          dd {
            float: left;
            width: 33%;
            text-align: center;
          }
        }
        .header-meishi {
          width: 156px;
          dd {
            float: left;
            width: 50%;
            text-align: center;
          }
        }
        .header-movie {
          width: 90px;
        }
        .header-app {
          float: right;
          dd {
            display: inline-block;
            margin: 0 8px;
            .appicon {
              width: 60px;
              height: 60px;
              border: 0;
            }
          }
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
