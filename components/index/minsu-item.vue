<template>
  <div class="minsu-item">
    <nuxt-link to="/">
      <div class="product-card-header">
        <img :src="product.coverImage" alt="" class="product-img">
        <img src="https://hz.meituan.com/null@200w_200h_1e_1c" alt="" class="head-img">
      </div>
      <div class="product-info">
        <p class="product-title">
          {{ product.title }}
        </p>
        <p class="sub-title">
          <span>整套{{ product.layoutRoom }}居室·</span>
          <span>可住{{ product.maxGuestNumber }}人 | </span>
          <span>{{ product.locationArea }}</span>
        </p>
        <p class="price-number numfont price">
          <span class="price-icon">￥</span>
          <span>{{ product.price }}</span>
        </p>
      </div>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'MinsuItem',
  components: {},
  mixins: [],
  props: {
    product: {
      type: Object,
      required: true
    }
  },
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
@import '~assets/css/variables.scss';

.minsu-item {
  float: left;
  margin-right: 18px;
  .product-card-header {
    position: relative;
    .product-img {
      margin-bottom: 11px;
      width: 370px;
      height: 208px;
      max-width: 100%;
      background: url(//p0.meituan.net/travelcube/214b8411190e874781fe91dd3096236211567.png);
      background-size: cover;
      background-position: 50%;
      border-radius: 4px;
      cursor: pointer;
    }
    .head-img {
      position: absolute;
      bottom: -12px;
      right: 15px;
      width: 48px;
      height: 48px;
      border-radius: 40px;
      background-image: url('https://p0.meituan.net/mmc/35ad1f9253761ea6ff822b5e659f234f3758.png');
      background-size: 100%;
      background-position: 50% 50%;
      background-repeat: no-repeat;
      border: 2px solid $border-color-white;
    }
  }
  .product-info {
    padding-bottom: 25px;
    .product-title {
      margin: 7px 0;
      width: 297px;
      font-size: 16px;
      color: $color-text-primary;
      font-weight: 400;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
    }
    .sub-title {
      font-size: 12px;
      color: $color-text-secondary;
    }
    .price {
      padding: 4px 0;
      font-size: 22px;
      color: #FF6600;
      font-weight: 500;
      letter-spacing: -.8px;
      .price-icon {
        font-size: 14px;
      }
    }
  }
}
</style>
