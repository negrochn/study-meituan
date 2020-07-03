<template>
  <div class="page index">
    <div class="index-container">
      <Banner />
      <Maoyan />
      <Zhenguo />
      <Recommend />
    </div>
  </div>
</template>

<script>
import Banner from '@/components/index/banner'
import Maoyan from '@/components/index/maoyan'
import Zhenguo from '@/components/index/zhenguo'
import Recommend from '@/components/index/recommend'

export default {
  name: 'Index',
  components: {
    Banner,
    Maoyan,
    Zhenguo,
    Recommend
  }
}
</script>

<style lang="scss" scoped>
.page.index {
  line-height: initial;
  .index-container {
    margin: 0 auto;
    width: 1190px;
  }
}
</style>
