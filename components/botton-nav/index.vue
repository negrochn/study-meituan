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
              {{ classify.label }}
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
        { label: '酒店' },
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

</style>
