<template>
  <div :style="`background: ${background};`" class="index-nav-container">
    <ul>
      <li class="title nav-item mf-shang-hei-regular">
        {{ title }}
      </li>
      <li v-for="item in list" :key="item.label" :class="['nav-item', { 'active': label === item.label }]" @mouseenter="onMouseEnter">
        {{ item.label }}
      </li>
      <li v-if="path" class="total nav-item">
        <nuxt-link :to="path">
          <span>全部</span>
          <span class="right-arrow iconfont icon-btn_right" />
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'IndexNavContainer',
  props: {
    title: {
      type: String,
      required: true
    },
    background: {
      type: String,
      default: '#ccc'
    },
    list: {
      type: Array,
      default: () => []
    },
    label: {
      type: String,
      default: ''
    },
    path: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      timer: null
    }
  },
  methods: {
    onMouseEnter (e) {
      clearTimeout(this.timer)
      this.timer = setTimeout(() => {
        this.$emit('on-mouseenter', e.target.textContent.trim())
      }, 100)
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.index-nav-container {
  box-sizing: border-box;
  width: 100%;
  height: 44px;
  line-height: 44px;
  font-size: 14px;
  color: $color-text-white;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  .title {
    font-size: 18px;
    margin-left: 13px;
    margin-right: 10px;
  }
  .nav-item {
    position: relative;
    float: left;
    padding: 0 5px;
    cursor: pointer;
    text-transform: uppercase;
    &.active:after {
      content: " ";
      position: absolute;
      display: block;
      top: 37px;
      left: 0;
      right: 0;
      margin: auto;
      width: 2px;
      height: 0;
      border-left: 5px solid transparent;
      border-right: 5px solid transparent;
      border-bottom: 7px solid $border-color-white;
    }
  }
  .total {
    float: right;
    margin-right: 12px;
    a {
      color: $color-text-white;
    }
  }
  .right-arrow {
    display: inline-block;
    transform: scale(.8);
  }
}
.mf-shang-hei-regular {
  font-family: "MFShangHei-Regular" !important;
}
</style>
