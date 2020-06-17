<template>
  <div class="left-banner">
    <div class="category-nav-container">
      <div class="category-nav-title-wrapper">
        <span class="category-nav-title">全部分类</span>
        <span class="title-icon" />
      </div>
      <div class="category-nav-content-wrapper">
        <ul>
          <li v-for="item in navList" :key="item.id" class="nav-li">
            <i :class="`iconfontNew hc-icon-${item.id}`" />
            <span class="nav-text-wrapper">
              <span v-for="(itm, idx) in item.children" :key="itm.label">
                <nuxt-link :to="itm.path" class="nav-text">
                  <span>{{ itm.label }}</span>
                  <span v-if="itm.promotion" class="nav-promotion">
                    {{ itm.promotion }}
                  </span>
                </nuxt-link>
                <span v-if="idx !== item.children.length - 1"> / </span>
              </span>
            </span>
            <i class="nav-right-arrow" />
          </li>
        </ul>
      </div>
      <div class="category-nav-detail-wrapper" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'LeftBanner',
  data () {
    return {
      navList: [
        {
          id: 'foodNew',
          children: [
            { label: '美食', path: '/meishi' }
          ]
        },
        {
          id: 'waimaiNew',
          children: [
            { label: '外卖', path: '/waimai' }
          ]
        },
        {
          id: 'hotelNew',
          children: [
            { label: '酒店', path: '/hotel', promotion: 'HOT' }
          ]
        },
        {
          id: 'zhenguoNew',
          children: [
            { label: '民宿', path: '/minsu' }
          ]
        },
        {
          id: 'maoyanNew',
          children: [
            { label: '猫眼电影', path: '/maoyan' }
          ]
        },
        {
          id: 'planeNew',
          children: [
            { label: '机票', path: '/flight' },
            { label: '火车票', path: '/train' }
          ]
        },
        {
          id: 'ktvNew',
          children: [
            { label: '休闲娱乐', path: '/xiuxianyule' },
            { label: 'KTV', path: '/xiuxianyule/c10' }
          ]
        },
        {
          id: 'lifeNew',
          children: [
            { label: '生活服务', path: '/shenghuo' }
          ]
        },
        {
          id: 'beautyNew',
          children: [
            { label: '丽人', path: '/jiankangliren' },
            { label: '美发', path: '/jiankangliren/c74' },
            { label: '医学美容', path: '/jiankangliren/c20423' }
          ]
        },
        {
          id: 'marriedNew',
          children: [
            { label: '结婚', path: '/jiehun' },
            { label: '婚纱摄影', path: '/jiehun/c20198' },
            { label: '婚宴', path: '/jiehun/c20210' }
          ]
        },
        {
          id: 'childNew',
          children: [
            { label: '亲子', path: '/qinzi' },
            { label: '儿童乐园', path: '/qinzi/c20108' },
            { label: '幼教', path: '/qinzi/c20045' }
          ]
        },
        {
          id: 'sportNew',
          children: [
            { label: '运动健身', path: '/youyongjianshen' },
            { label: '健身中心', path: '/youyongjianshen/c20253' }
          ]
        },
        {
          id: 'decorateNew',
          children: [
            { label: '家装', path: '/jiazhuang' },
            { label: '建材', path: '/jiazhuang/c20182' },
            { label: '家居', path: '/jiazhuang/c20771' }
          ]
        },
        {
          id: 'educationNew',
          children: [
            { label: '学习培训', path: '/jiaoyupeixun' },
            { label: '音乐培训', path: '/xuexipeixun/c20287' }
          ]
        },
        {
          id: 'medicalNew',
          children: [
            { label: '医疗健康', path: '/yiliao' },
            { label: '宠物', path: '/chongwu/c20691' },
            { label: '爱车', path: '/aiche' }
          ]
        },
        {
          id: 'barNew',
          children: [
            { label: '酒吧', path: '/xiuxianyule/c234' },
            { label: '密室逃脱', path: '/xiuxianyule/c230' }
          ]
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.left-banner {
  float: left;
  .category-nav-container {
    position: relative;
    float: left;
    box-sizing: border-box;
    margin-top: -50px;
    width: 230px;
    height: 475px;
    background: $color-white;
    color: $color-text-regular - $color-text-span2;
    border: 1px solid $border-color-base;
    .category-nav-title-wrapper {
      box-sizing: border-box;
      padding-top: 15px;
      height: 50px;
      .category-nav-title {
        margin-left: 15px;
        color: $color-text-primary;
        font-size: 16px;
        font-weight: 700;
      }
    }
    .category-nav-content-wrapper {
      ul {
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding: 10px 0 8px;
        height: 425px;
      }
    }
    .nav-li {
      position: relative;
      box-sizing: border-box;
      padding: 2px 12px;
      height: 26px;
      &:hover {
        background: rgba(255, 150, 0, 0.08);
        color: $color-text-primary;
        a {
          font-weight: 700;
        }
        .nav-text {
          color: $color-text-primary;
        }
        .nav-right-arrow {
          color: $color-text-primary;
          border-bottom: 1px solid $color-text-primary;
          border-right: 1px solid $color-text-primary;
        }
        .nav-promotion {
          font-weight: 400;
          background: linear-gradient(to bottom right, #FFD000, #FFBD00);
        }
      }
      .nav-right-arrow {
        position: absolute;
        display: block;
        top: 0;
        bottom: 0;
        right: 13px;
        margin: auto;
        width: 4px;
        height: 4px;
        color: #BFBFBF;
        border-bottom: 1px solid #BFBFBF;
        border-right: 1px solid #BFBFBF;
        transform: rotate(-45deg);
      }
    }
    .nav-text-wrapper {
      display: inline-block;
      margin-left: 11px;
    }
    .iconfontNew:before {
      display: inline-block;
      width: 16px;
      height: 16px;
      font-size: 16px;
    }
    .nav-text {
      height: 20px;
      line-height: 20px;
      font-size: 13px;
      color: #646464;
      cursor: pointer;
    }
    .nav-promotion {
      position: relative;
      display: inline-block;
      margin-left: 5px;
      padding: 0 7px;
      background: #FFF3CC;
      font-size: 12px;
      color: $color-text-primary;
      border-radius: 10px;
      transform: scale(.9);
      opacity: 1;
    }
  }
}
</style>
