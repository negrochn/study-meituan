<template>
  <div class="recommend-container">
    <IndexNavContainer
      title="猜你喜欢"
      background="linear-gradient(to right, rgb(88, 174, 221) 2%, rgb(66, 191, 205) 97%) rgb(88, 174, 221);"
      :list="indexNavList"
      :label="curRecommendClassify"
    />
    <div class="recommend-list">
      <RecommendItem />
      <nuxt-link v-for="recommend in recommendList" :key="recommend.itemId" :to="`/xiuxianyule/${recommend.itemId}`" class="recommend-item">
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
    </div>
  </div>
</template>

<script>
import IndexNavContainer from './index-nav-container'
import RecommendItem from './recommend-item'
import Score from './score'

export default {
  name: 'Recommend',
  components: {
    IndexNavContainer,
    RecommendItem,
    Score
  },
  data () {
    return {
      indexNavList: [
        { label: '为你甄选最适合的' }
      ],
      curRecommendClassify: '为你甄选最适合的',
      recommendList: [
        {
          itemId: '560649580',
          title: '网鱼网咖（花园岗店）',
          imgUrl: 'http://p0.meituan.net/w.h/joymerchant/1587726507938194581-3043341-1538042248059.jpg',
          score: '4.1',
          consumeNum: null,
          areaName: '石祥路/沈半沿线',
          lowPrice: '29.0',
          saleNum: null,
          commentNum: 13,
          detailUrl: '',
          firstCate: [
            2,
            3,
            20630,
            20873,
            20426
          ],
          avgPrice: 0
        },
        {
          itemId: '52656674',
          title: '乐刻运动健身（水晶城购物中心店）',
          imgUrl: 'https://p0.meituan.net/w.h/dpmerchantpic/e1845c6780938ef9f222685447bb346a178451.jpg',
          score: '4.0',
          consumeNum: null,
          areaName: '水晶城购物中心',
          lowPrice: '1.9',
          saleNum: null,
          commentNum: 50,
          detailUrl: '',
          firstCate: [
            2,
            20611,
            20873,
            20426,
            20252
          ],
          avgPrice: 99
        },
        {
          itemId: '41494011',
          title: '私人订制（下沙宝龙城市广场店）',
          imgUrl: 'https://p0.meituan.net/w.h/wedding/cafbb04603c80a2c9f8e9591b0e6aded504317.jpg',
          score: '5.0',
          consumeNum: null,
          areaName: '下沙宝龙城市广场',
          lowPrice: '35.0',
          saleNum: null,
          commentNum: 1821,
          detailUrl: '',
          firstCate: [
            20611,
            22,
            20630,
            20426
          ],
          avgPrice: 145
        },
        {
          itemId: '1704602',
          title: '蕾蕾美颜美容美体（越都荟店）',
          imgUrl: 'https://p0.meituan.net/w.h/dpmerchantpic/c3799f6c387315264dacfdc65e92e753266901.jpg',
          score: '4.8',
          consumeNum: null,
          areaName: '浙一医院/庆春路沿线',
          lowPrice: '138.0',
          saleNum: null,
          commentNum: 245,
          detailUrl: '',
          firstCate: [
            20611,
            22,
            20426
          ],
          avgPrice: 154
        },
        {
          itemId: '74900221',
          title: '因为遇见你烤肉海鲜自助餐厅',
          imgUrl: 'http://p1.meituan.net/w.h/mogu/c9e040b5741d7b3af5bd1028e1d5bdd778428.jpg',
          score: '3.6',
          consumeNum: null,
          areaName: '宝龙城市广场',
          lowPrice: '64.0',
          saleNum: null,
          commentNum: 13511,
          detailUrl: '',
          firstCate: [
            1,
            20632,
            20426,
            20557
          ],
          avgPrice: 56
        },
        {
          itemId: '95404458',
          title: '小桑树染烫改变专门店（下城区晶晖店）',
          imgUrl: 'https://p1.meituan.net/w.h/dpmerchantpic/80106cfd519b2af34313987a4ac82991108967.jpg',
          score: '5.0',
          consumeNum: null,
          areaName: '西湖文化广场',
          lowPrice: '28.0',
          saleNum: null,
          commentNum: 902,
          detailUrl: '',
          firstCate: [
            20611,
            22,
            20630,
            20426
          ],
          avgPrice: 231
        },
        {
          itemId: '4085553',
          title: '江南玉璞（滨江星耀城店）',
          imgUrl: 'http://p0.meituan.net/w.h/joymerchant/4ac51c785ac310a22783d174377af298-66830910.jpg',
          score: '4.4',
          consumeNum: null,
          areaName: '星耀城',
          lowPrice: '89.0',
          saleNum: null,
          commentNum: 4164,
          detailUrl: '',
          firstCate: [
            2,
            3,
            20611,
            20426
          ],
          avgPrice: 254
        },
        {
          itemId: '2749994',
          title: '可莎蜜兒（临平2店）',
          imgUrl: 'http://p1.meituan.net/w.h/bbia/cfc2bce9326c0c067e1a7963d44df7d8118994.jpg',
          score: '4.2',
          consumeNum: null,
          areaName: '临平老街',
          lowPrice: '141.0',
          saleNum: null,
          commentNum: 177,
          detailUrl: '',
          firstCate: [
            1,
            20426,
            20557
          ],
          avgPrice: 35
        },
        {
          itemId: '40802028',
          title: '憨大叔韩式儿童摄影 38店连锁（萧山店）',
          imgUrl: 'http://p0.meituan.net/w.h/wedding/5b723f77d8b69a4716227f9b501be1e8155886.jpg',
          score: '4.9',
          consumeNum: null,
          areaName: '旺角城/银隆百货',
          lowPrice: '499.0',
          saleNum: null,
          commentNum: 1380,
          detailUrl: '',
          firstCate: [
            20007,
            20426,
            29
          ],
          avgPrice: 629
        },
        {
          itemId: '2477349',
          title: '丹比艺术蛋糕（世纪大道店）',
          imgUrl: 'http://p1.meituan.net/w.h/bbia/afe1fcd06b3f9bdddcbe50868a3dce01126683.jpg',
          score: '4.1',
          consumeNum: null,
          areaName: '',
          lowPrice: '2.0',
          saleNum: null,
          commentNum: 1419,
          detailUrl: '',
          firstCate: [
            1,
            20426,
            20557
          ],
          avgPrice: 28
        },
        {
          itemId: '4627270',
          title: '品凯口腔固陵路门诊',
          imgUrl: 'http://p0.meituan.net/w.h/joymerchant/959a3f87e941ec09e4aaa51d9546c95f-2063176866.jpg',
          score: '4.1',
          consumeNum: null,
          areaName: '',
          lowPrice: '68.0',
          saleNum: null,
          commentNum: 768,
          detailUrl: '',
          firstCate: [
            20274,
            3,
            20630
          ],
          avgPrice: 117
        },
        {
          itemId: '93361172',
          title: '厨禾（星火南路店）',
          imgUrl: 'http://p1.meituan.net/w.h/deal/5d8bf2b44418a6870b96bb183b8c64a0152241.jpg',
          score: '4.9',
          consumeNum: null,
          areaName: '临平老街',
          lowPrice: '88.0',
          saleNum: null,
          commentNum: 4757,
          detailUrl: '',
          firstCate: [
            1,
            20632,
            20426,
            20557
          ],
          avgPrice: 61
        },
        {
          itemId: '6641013',
          title: '爱情故事·养生SPA会所（新侨店）',
          imgUrl: 'http://p1.meituan.net/w.h/joymerchant/6723736936787274858.jpg',
          score: '5.0',
          consumeNum: null,
          areaName: '湖滨/解百商厦',
          lowPrice: '318.0',
          saleNum: null,
          commentNum: 1053,
          detailUrl: '',
          firstCate: [
            2,
            3,
            20611,
            20426
          ],
          avgPrice: 381
        },
        {
          itemId: '114313672',
          title: '御隆汤水世界',
          imgUrl: 'https://p1.meituan.net/w.h/dpmerchantpic/c766857630181c5b723bdf6afa3a4644151352.jpg',
          score: '4.1',
          consumeNum: null,
          areaName: '高沙商业街',
          lowPrice: '9.9',
          saleNum: null,
          commentNum: 12234,
          detailUrl: '',
          firstCate: [
            2,
            3,
            20611,
            20426
          ],
          avgPrice: 121
        },
        {
          itemId: '168927026',
          title: '卢金文烤鱼·龙虾·炭锅鸡（下沙学林街店）',
          imgUrl: 'https://img.meituan.net/w.h/msmerchant/f857f2e91c0d2661200ac92f1d01a795862507.jpg',
          score: '5.0',
          consumeNum: null,
          areaName: '高沙商业街',
          lowPrice: '69.0',
          saleNum: null,
          commentNum: 535,
          detailUrl: '',
          firstCate: [
            1,
            20632,
            20426,
            20557
          ],
          avgPrice: 58
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.recommend-container {
  margin: 40px auto 0;
  width: 100%;
  .recommend-list {
    box-sizing: border-box;
    padding: 10px 10px 20px;
    width: 100%;
    max-height: 758px;
    background-color: $color-white;
    border: 1px solid $border-color-base;
    border-top: 0;
    border-bottom-left-radius: 4px;
    border-bottom-right-radius: 4px;
    overflow: hidden;
    text-align: left;
    .recommend-item {
      box-sizing: border-box;
      display: inline-block;
      width: 20%;
      vertical-align: middle;
      .card-container {
        padding: 10px;
        &:hover {
          background: #f4f4f4;
          border-radius: 4px;
          transition: background-color .5s;
        }
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
      background-color: #f4f4f4;
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
          color: #FF6600;
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
}
</style>
