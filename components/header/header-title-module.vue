<template>
  <div class="header-title-module">
    <div class="header-title">
      <nuxt-link to="/">
        <img src="//s0.meituan.net/bs/fe-web-meituan/fa5f0f0/img/logo.png" alt="美团">
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeaderTitleModule',
  components: {},
  mixins: [],
  props: {},
  data () {
    return {}
  },
  computed: {},
  watch: {},
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style lang="scss" scoped>
.header-title-module {
  float: left;
  padding: 28px 60px 40px 0;
  min-width: 220px;
  height: 54px;
  font-size: 16px;
  .header-title {
    display: inline-block;
    a {
      img {
        width: 126px;
        height: 46px;
        border: 0;
      }
    }
  }
}
</style>
