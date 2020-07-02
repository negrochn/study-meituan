<template>
  <div class="maoyan-container">
    <IndexNavContainer
      title="猫眼电影"
      background="linear-gradient(to right, rgb(250, 60, 104) 2%, rgb(254, 70, 77) 97%) rgb(250, 60, 104);"
      :list="filmClassifyList"
      :label="curFilmClassify"
      path="/maoyan"
    />
    <div class="scenes-body">
      <!-- hor-container 暂未开发 -->
      <div class="hot-container" />
      <div class="coming-container">
        <div>
          <div class="slider">
            <div :style="`left: ${sliderContentLeft}px; margin: 0 12px;`" class="slider-content clearfix">
              <div v-for="film in comingFilmList" :key="film.path" class="slider-item-film">
                <nuxt-link :to="film.path">
                  <img :src="film.imgSrc" alt="" class="image film-img">
                  <div class="film-info">
                    <p class="film-score">
                      <b>
                        <span>{{ film.wishNum }}</span>
                        人想看
                      </b>
                    </p>
                    <p class="film-name">
                      {{ film.filmName }}
                    </p>
                  </div>
                </nuxt-link>
              </div>
            </div>
            <div style="right: 0;" class="btn btn-next" @click="onNextClick">
              <i class="iconfont icon-btn_right" />
            </div>
            <div style="left: 0;" class="btn btn-pre" @click="onPreClick">
              <i class="iconfont icon-btn_left" />
            </div>
          </div>
          <div class="slider-pagination" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import IndexNavContainer from './index-nav-container'

export default {
  name: 'Maoyan',
  components: {
    IndexNavContainer
  },
  data () {
    return {
      filmClassifyList: [
        { label: '即将上映' }
      ],
      curFilmClassify: '即将上映',
      comingFilmList: [
        {
          filmName: '沉香',
          path: '/maoyan/films/1318812',
          imgSrc: '//p0.meituan.net/movie/6adbe9c365a3aaadfb65910bc279bf6a3385927.jpg@214w_297h_1e_1c',
          wishNum: 1773
        },
        {
          filmName: '致命复活',
          path: '/maoyan/films/1247400',
          imgSrc: '//p0.meituan.net/movie/f1210412ff52740cfbc3cca8212834bd406835.jpg@214w_297h_1e_1c',
          wishNum: 632
        },
        {
          filmName: '天下无拐',
          path: '/maoyan/films/1222268',
          imgSrc: '//p0.meituan.net/movie/a19913517ec4dd7b1e8c56a199ceaa4280560.jpg@214w_297h_1e_1c',
          wishNum: 12449
        },
        {
          filmName: '恋上美人鱼',
          path: '/maoyan/films/665702',
          imgSrc: '//p1.meituan.net/movie/eb37c5b78ec0c14aaad707700fcc1443390529.jpg@214w_297h_1e_1c',
          wishNum: 2667
        },
        {
          filmName: '拆弹专家2',
          path: '/maoyan/films/1218142',
          imgSrc: '//p1.meituan.net/movie/ccea56ae49249d482be5997aa98e94691344390.jpg@214w_297h_1e_1c',
          wishNum: 61949
        },
        {
          filmName: '我想静静',
          path: '/maoyan/films/343130',
          imgSrc: '//p0.meituan.net/movie/fd0e0e48f13236ed671f3df0e4ba7429200080.jpg@214w_297h_1e_1c',
          wishNum: 6425
        },
        {
          filmName: '北平会馆',
          path: '/maoyan/films/1301478',
          imgSrc: '//p0.meituan.net/movie/644b66958ccbeb8bac4955c52864c8881471793.jpg@214w_297h_1e_1c',
          wishNum: 24483
        },
        {
          filmName: '通往春天的列车',
          path: '/maoyan/films/1219866',
          imgSrc: '//p0.meituan.net/moviemachine/331c70099c5728d53694009426fb84ba165027.jpg@214w_297h_1e_1c',
          wishNum: 8823
        },
        {
          filmName: '赤狐书生',
          path: '/maoyan/films/1277751',
          imgSrc: '//p1.meituan.net/movie/7d4e340665573384faa2f2e34b705b73977180.jpg@214w_297h_1e_1c',
          wishNum: 23539
        },
        {
          filmName: '哪吒重生',
          path: '/maoyan/films/1299124',
          imgSrc: '//p0.meituan.net/movie/d8bba55fde322a809b6eeb95ddbffec82554093.jpg@214w_297h_1e_1c',
          wishNum: 9720
        }
      ],
      sliderContentLeft: 0
    }
  },
  methods: {
    slide (step = 1165) {
      const length = this.comingFilmList.length
      const filmWidth = (214 + 19) * length
      const computedWidth = this.sliderContentLeft - step
      // 限制上一页下一页仅在有效的范围内点击
      if (computedWidth <= 0 && Math.abs(computedWidth) < filmWidth) {
        this.sliderContentLeft = computedWidth
      }
    },
    onNextClick () {
      this.slide()
    },
    onPreClick () {
      this.slide(-1165)
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.maoyan-container {
  position: relative;
  margin: 40px auto 0;
  .slider {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    .slider-content {
      position: relative;
      width: 10000000px;
      height: 100%;
      transition: left .5s ease-out;
      .slider-item-film {
        position: relative;
        float: left;
        margin-right: 19px;
        width: 214px;
        height: 297px;
        background-size: 100%;
        background-position: 50%;
        background-repeat: no-repeat;
        .film-img {
          width: 100%;
          height: 100%;
          border-radius: 4px;
        }
        .film-info {
          position: absolute;
          bottom: 0;
          width: 100%;
          height: 100px;
          border-bottom-left-radius: 4px;
          border-bottom-right-radius: 4px;
          background-image: linear-gradient(-180deg, rgba(0,0,0,0.00) 0%, rgba(29,45,55,0.80) 99%);
          .film-score {
            margin-top: 48px;
            padding-left: 10px;
            font-size: 12px;
            color: $color-white;
            font-weight: 500;
            text-align: left;
            span {
              font-size: 16px;
              color: #FD9827;
              font-weight: 500;
            }
          }
          .film-name {
            padding-left: 10px;
            width: 6em;
            font-size: 16px;
            color: $color-white;
            font-weight: 500;
            text-align: left;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
          }
        }
      }
    }
    .btn {
      position: absolute;
      width: 40px;
      height: 40px;
      background: #333;
      top: 43%;
      text-align: center;
      border-radius: 40px;
      transition: opacity .5s;
      transform: scale(.95);
      opacity: 0;
      cursor: pointer;
      .iconfont {
        line-height: 40px;
        font-size: 20px;
        color: $color-white;
        text-align: center;
      }
    }
    &:hover {
      .btn {
        opacity: .8;
        transition: opacity .5s;
      }
    }
  }
}
</style>
