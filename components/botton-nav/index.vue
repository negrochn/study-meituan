<template>
  <nav class="botton-nav">
    <div class="title">
      美团导航
    </div>
    <dl class="b-n-content">
      <div class="b-n-classification">
        <dt class="b-n-subtitle">
          热门城市
        </dt>
        <div class="b-n-sublist">
          <dd v-for="city in hotCityList" :key="city.label" class="b-n-list-item">
            <nuxt-link to="/">
              {{ city.label }}
            </nuxt-link>
          </dd>
        </div>
      </div>
      <div class="b-n-classification">
        <dt class="b-n-subtitle">
          热门分类
        </dt>
        <div class="b-n-sublist">
          <dd v-for="classify in hotClassifyList" :key="classify.label" class="b-n-list-item">
            <nuxt-link to="/">
              <span>{{ classify.label }}</span>
              <span v-if="classify.promotion" class="nav-promotion">{{ classify.promotion }}</span>
            </nuxt-link>
          </dd>
        </div>
      </div>
      <div class="b-n-classification">
        <dt class="b-n-subtitle">
          周边热门
        </dt>
        <div class="b-n-sublist">
          <dd v-for="surrounding in hotSurroundingList" :key="surrounding.label" class="b-n-list-item">
            <nuxt-link to="/">
              {{ surrounding.label }}
            </nuxt-link>
          </dd>
        </div>
      </div>
    </dl>
  </nav>
</template>

<script>
export default {
  name: 'BottonNav',
  data () {
    return {
      hotCityList: [
        { label: '苏州' },
        { label: '南宁' },
        { label: '昆明' },
        { label: '北京' },
        { label: '天津' },
        { label: '济南' },
        { label: '南京' },
        { label: '无锡' },
        { label: '长沙' },
        { label: '青岛' },
        { label: '太原' },
        { label: '哈尔滨' },
        { label: '石家庄' },
        { label: '温州' },
        { label: '东莞' },
        { label: '常州' },
        { label: '成都' },
        { label: '长春' },
        { label: '佛山' },
        { label: '广州' }
      ],
      hotClassifyList: [
        { label: '酒店', promotion: 'HOT' },
        { label: '美食' },
        { label: '休闲娱乐' },
        { label: '运动健身' },
        { label: '生活服务' },
        { label: '上门服务' },
        { label: '购物' },
        { label: '时尚购' },
        { label: '本地购物' },
        { label: '结婚' },
        { label: '摄影写真' },
        { label: '宴会' },
        { label: '丽人' },
        { label: '母婴亲子' },
        { label: '学习培训' },
        { label: '家装' },
        { label: '汽车服务' },
        { label: '医疗' },
        { label: '宠物' }
      ],
      hotSurroundingList: [
        { label: '德清酒店' },
        { label: '德清美食' },
        { label: '临安休闲娱乐' },
        { label: '德清运动健身' },
        { label: '德清生活服务' },
        { label: '富阳上门服务' },
        { label: '临安购物' },
        { label: '富阳时尚购' },
        { label: '富阳本地购物' },
        { label: '临安结婚' },
        { label: '临安摄影写真' },
        { label: '德清宴会' },
        { label: '临安丽人' },
        { label: '富阳母婴亲子' },
        { label: '临安学习培训' },
        { label: '德清家装' },
        { label: '富阳汽车服务' },
        { label: '德清医疗' },
        { label: '德清宠物' }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.botton-nav {
  margin: 40px auto 0;
  width: 1190px;
  height: auto;
  background: $bg-color-white;
  border: 1px solid $border-color-base;
  border-radius: 4px;
  .title {
    padding-top: 6px;
    padding-left: 20px;
    width: auto;
    height: 44px;
    line-height: 44px;
    font-size: 16px;
    color: $color-text-primary;
    font-weight: 500;
    border-top-left-radius: 4px;
    border-top-right-radius: 4px;
  }
  .b-n-content {
    width: 100%;
    height: auto;
    .b-n-classification {
      width: 100%;
      height: auto;
      overflow: hidden;
      .b-n-subtitle {
        float: left;
        padding: 10px 0;
        width: 100px;
        height: 100%;
        line-height: initial;
        color: $color-text-primary;
        font-size: 14px;
        font-weight: 500;
        text-align: center;
      }
      .b-n-sublist {
        float: left;
        padding-top: 12px;
        width: 1090px;
        height: auto;
        border-bottom: 1px solid $border-color-base;
        overflow: hidden;
        .b-n-list-item {
          float: left;
          margin-bottom: 13px;
          width: 100px;
          height: 17px;
          font-size: 12px;
          a {
            display: block;
            width: 80px;
            line-height: initial;
            color: $color-text-regular;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            cursor: pointer;
            &:hover {
              color: #fe8c00;
            }
          }
          .nav-promotion {
            position: relative;
            top: -1px;
            margin: 0 5px;
            padding: 0 6px;
            background: #FF4848;
            font-size: 12px;
            color: $color-text-white;
            font-weight: 400;
            border-radius: 10px;
          }
        }
      }
      &:last-child {
        .b-n-sublist {
          border-bottom: none;
        }
      }
    }
  }
}
</style>
