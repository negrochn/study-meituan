<template>
  <div class="header-search-module">
    <div class="header-search-block">
      <input
        class="header-search-input"
        type="text"
        placeholder="搜索商家或地点"
        @focus="isSuggestShow = true"
        @blur="onBlur"
        @keyup="onKeyup"
      >
      <button class="header-search-btn">
        <span class="header-icon icon-search-new" />
      </button>
    </div>
    <div v-show="isSuggestShow" class="header-search-suggest">
      <div v-show="!hasInput" class="header-search-noinput">
        <div class="header-search-history">
          <h6>最近搜索</h6>
          <span class="header-search-clean">删除搜索历史</span>
          <ul>
            <li v-for="item in historyList" :key="item.label">
              <nuxt-link :to="item.path">
                {{ item.label }}
              </nuxt-link>
            </li>
          </ul>
        </div>
        <h6>热门搜索</h6>
        <div class="header-search-hotword" />
      </div>
      <div v-show="hasInput" class="header-search-hasinput">
        <ul>
          <li v-for="item in searchResult" :key="item.label">
            <nuxt-link :to="item.path">
              {{ item.label }}
            </nuxt-link>
          </li>
        </ul>
      </div>
    </div>
    <div class="header-search-hotword" />
  </div>
</template>

<script>
export default {
  name: 'HeaderSearchModule',
  data () {
    return {
      isSuggestShow: false,
      historyList: [
        { label: '知味观', path: '/' },
        { label: '外婆家', path: '/' },
        { label: '山葵家', path: '/' },
        { label: '东极岛', path: '/' },
        { label: '杭州花圃', path: '/' },
        { label: '法喜寺', path: '/' }
      ],
      hasInput: false,
      searchResult: [
        { label: '杭州花圃', path: '/' },
        { label: '杭州花圃公交站', path: '/' },
        { label: '杭州花圃景区停车场', path: '/' }
      ]
    }
  },
  methods: {
    onBlur () {
      setTimeout(() => {
        this.isSuggestShow = false
      }, 100)
    },
    onKeyup (e) {
      this.hasInput = Boolean(e.target.value)
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~assets/css/variables.scss";

.header-search-module {
  position: absolute;
  float: left;
  left: 50%;
  padding-top: 28px;
  transform: translate(-50%);
  z-index: 999;
  .header-search-block {
    width: 550px;
    height: 40px;
    background: $bg-color-white;
    .header-search-input {
      box-sizing: border-box;
      padding: 15px;
      width: 85.45%;
      height: 100%;
      line-height: 100%;
      background: transparent;
      font-size: 14px;
      outline: none;
      border: 1px solid $border-color-base;
      border-right: none;
      border-radius: 4px 0 0 4px;
      &::placeholder {
        color: $color-text-secondary;
      }
    }
    .header-search-btn {
      float: right;
      box-sizing: border-box;
      width: 14.55%;
      height: 100%;
      line-height: 100%;
      background: $bg-color-header-search-btn;
      border: none;
      color: $color-text-primary;
      outline: none;
      border-bottom-right-radius: 4px;
      border-top-right-radius: 4px;
      cursor: pointer;
    }
  }
  .header-search-suggest {
    @include box-shadow($shadows);
    position: absolute;
    box-sizing: border-box;
    width: 85.45%;
    background: $bg-color-white;
    border: 1px solid $border-color-base;
    border-top: none;
    color: $color-text-secondary;
    font-size: 12px;
    text-align: left;
    z-index: 999;
    border-bottom-left-radius: 4px;
    border-bottom-right-radius: 4px;
    .header-search-noinput {
      padding: 10px;
      line-height: initial; // reset.css统一设置line-height: 1，此处需要重新设置
    }
    .header-search-hasinput {
      a {
        display: block;
        padding: 3px 10px;
        color: $color-text-primary + $color-text-primary;
        line-height: 1.6;
        cursor: pointer;
        &:hover {
          background: $bg-color-base;
          color: $color-link-hover;
        }
      }
    }
    h6 {
      font-size: 1em;
      font-weight: bold;
      padding-bottom: 5px;
    }
    .header-search-hotword {
      box-sizing: border-box;
      margin-bottom: 5px;
      padding-top: 5px;;
      padding-left: 0;
      width: auto;
      height: 25px;
      font-size: 12px;
      text-align: left;
      overflow: hidden;
    }
    .header-search-history {
      .header-search-clean {
        position: absolute;
        top: 10px;
        right: 10px;
        cursor: pointer;
      }
      ul {
        margin: 5px 3px 10px;
        li {
          display: inline-block;
          margin-right: 10px;
          a {
            @include a($color-text-regular);
            line-height: 1.6;
          }
        }
      }
    }
  }
  .header-search-hotword {
    box-sizing: border-box;
    padding-top: 8px;
    padding-left: 12px;
    width: 550px;
    height: 25px;
    text-align: left;
    overflow: hidden;
  }
}
</style>
