<template>
  <div class="page index">
    <div class="index-container">
      <Banner />
      <Maoyan />
      <Zhenguo />
    </div>
  </div>
</template>

<script>
import Banner from '@/components/index/banner'
import Maoyan from '@/components/index/maoyan'
import Zhenguo from '@/components/index/zhenguo'

export default {
  name: 'Index',
  components: {
    Banner,
    Maoyan,
    Zhenguo
  }
}
</script>

<style lang="scss" scoped>
.page.index {
  height: 2424px;
  line-height: initial;
  .index-container {
    margin: 0 auto;
    width: 1190px;
  }
}
</style>
