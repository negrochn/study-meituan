<template>
  <div class="page index">
    <Banner />
  </div>
</template>

<script>
import Banner from '@/components/index/banner'

export default {
  components: {
    Banner
  }
}
</script>

<style lang="scss" scoped>
.page.index {
  height: 1080px;
  line-height: initial;
  .index-container {
    margin: 0 auto;
    width: 1190px;
  }
}
</style>
