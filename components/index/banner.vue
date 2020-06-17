<template>
  <div class="index-container">
    <div class="banner-container clearfix">
      <LeftBanner />
      <RightBanner />
    </div>
  </div>
</template>

<script>
import LeftBanner from './left-banner'
import RightBanner from './right-banner'

export default {
  name: 'Banner',
  components: {
    LeftBanner,
    RightBanner
  }
}
</script>

<style lang="scss" scoped>
</style>
