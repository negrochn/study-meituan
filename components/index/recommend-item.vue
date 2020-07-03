<template>
  <nuxt-link :to="`/xiuxianyule/${recommend.itemId}`" class="recommend-item">
    <div class="card-container">
      <div class="recommend-card-wrapper">
        <div class="img-box">
          <img :src="recommend.imgUrl.replace('/w.h', '') + '@214w_120h_1e_1c'" alt="" class="image">
        </div>
        <div class="info-box">
          <div :title="recommend.title" class="title aligned">
            {{ recommend.title }}
          </div>
          <div class="score-line aligned">
            <Score :score="recommend.score" />
            <div class="comment-number">
              {{ recommend.commentNum }}个评价
            </div>
          </div>
          <div class="desc-line aligned">
            <div v-if="recommend.areaName" class="desc">
              {{ recommend.areaName }}
            </div>
          </div>
          <div class="bottom-line aligned">
            <div class="price-box">
              <span>
                <span class="yuan">￥</span>
                <span class="price-number numfont">{{ recommend.lowPrice }}</span>
                <span class="price-desc">起</span>
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nuxt-link>
</template>

<script>
import Score from './score'

export default {
  name: 'RecommendItem',
  components: {
    Score
  },
  mixins: [],
  props: {
    recommend: {
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

.recommend-item {
  box-sizing: border-box;
  display: inline-block;
  width: 20%;
  vertical-align: middle;
  .card-container {
    padding: 10px;
    &:hover {
      background: $bg-color-reommend-card-hover;
      border-radius: 4px;
      transition: background-color .5s;
    }
  }
}

.recommend-card-wrapper {
  box-sizing: border-box;
  width: 100%;
  .img-box {
    padding-bottom: 56.25%;
    width: 100%;
    height: 0;
    background-color: $bg-color-reommend-card-hover;
    background-image: url(//p0.meituan.net/travelcube/214b8411190e874781fe91dd3096236211567.png);
    background-size: cover;
    background-position: 50% 50%;
    border-radius: 4px;
    overflow: hidden;
    img {
      width: 100%;
      font-size: 0;
    }
  }
  .info-box {
    position: relative;
    margin-top: 10px;
    .title {
      margin: 0;
      width: 100%;
      line-height: 20px;
      font-size: 14px;
      color: $color-text-primary;
      font-weight: 500;
    }
    .title.aligned {
      width: 100%;
      height: 22px;
      line-height: 22px;
      font-size: 16px;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
    }
    .score-line {
      div {
        display: inline-block;
      }
      .comment-number {
        margin-left: 10px;
        height: 24px;
        line-height: 24px;
        font-size: 12px;
        color: $color-text-secondary;
      }
    }
    .score-line.aligned {
      height: 24px;
    }
    .desc-line.aligned {
      height: 18px;
      .desc {
        margin-top: 4px;
        width: 100%;
        height: 18px;
        line-height: 18px;
        font-size: 12px;
        color: $color-text-secondary;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
    }
    .bottom-line {
      .price-box {
        color: $color-text-price;
        .yuan {
          font-size: 14px;
          font-weight: 700;
        }
        .price-number {
          font-size: 22px;
          letter-spacing: .5;
        }
        .price-desc {
          margin-left: 4px;
          font-size: 12px;
          font-weight: 700;
        }
      }
      div {
        display: inline-block;
      }
    }
    .bottom-line.aligned {
      height: 28px;
    }
  }
}
.image {
  border: 0;
}
</style>
