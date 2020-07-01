<template>
  <footer class="com-footer">
    <div class="footer-content">
      <div class="footer-link clearfix">
        <div v-for="(column, index) in columnList" :key="index" class="footer-column">
          <dl v-for="link in column.linkList" :key="link.title">
            <dt>
              <nuxt-link v-if="link.path" :to="link.path">
                {{ link.title }}
              </nuxt-link>
              <span v-else>{{ link.title }}</span>
            </dt>
            <dd v-for="subLink in link.subLinkList" :key="subLink.label">
              <template v-if="subLink.value">
                <span>{{ subLink.label }}</span>
                <nuxt-link to="/">
                  <span>{{ subLink.value }}</span>
                </nuxt-link>
              </template>
              <nuxt-link v-else to="/">
                <span>{{ subLink.label }}</span>
              </nuxt-link>
            </dd>
          </dl>
        </div>
      </div>
      <div class="footer-copyright clearfix">
        <div class="footer-copyright-left">
          <p v-for="(copyright, index) in copyrightList" :key="index">
            <template v-for="link in copyright.linkList">
              <nuxt-link v-if="link.path" :key="link.label" :to="link.path">
                <span>{{ link.label }}</span>
              </nuxt-link>
              <span v-else :key="link.label" style="margin-right: 20px;">{{ link.label }}</span>
            </template>
          </p>
        </div>
        <div class="footer-copyright-right">
          <nuxt-link to="/">
            京公网安备11010502025545号
          </nuxt-link>
          <div class="footer-copyright-cert">
            <nuxt-link to="/" class="bus-license">
              <img src="https://p1.meituan.net/travelcube/3e7f8a17e55bace814166b667618b459366061.png@76h_76w_2e" alt="">
              <p>北京三快科技有限公司</p>
            </nuxt-link>
            <nuxt-link to="/" class="sp-ft sp-ft--record">
              备案信息
            </nuxt-link>
            <nuxt-link to="/" class="sp-ft sp-ft--knet">
              可信网站
            </nuxt-link>
            <nuxt-link to="/" class="sp-ft sp-ft--12315">
              12315消费争议
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  components: {},
  mixins: [],
  props: {},
  data () {
    return {
      columnList: [
        {
          linkList: [
            {
              title: '用户帮助',
              subLinkList: [
                { label: '申请退款' },
                { label: '查看美团券密码' },
                { label: '常见问题' },
                { label: '用户协议' },
                { label: '隐私政策' },
                { label: '反诈骗广告' },
                { label: '消费者权益保障' }
              ]
            },
            {
              title: '美团服务',
              subLinkList: [
                { label: '美团外卖' },
                { label: '美团酒店' },
                { label: '猫眼电影' },
                { label: '美团配送' },
                { label: '美团云' },
                { label: '大众点评' },
                { label: '美团民宿' },
                { label: '无人配送' }
              ]
            }
          ]
        },
        {
          linkList: [
            {
              title: '商家合作',
              subLinkList: [
                { label: '美团餐饮商户中心' },
                { label: '美食商家入驻(非外卖)' },
                { label: '美团外卖开店申请' },
                { label: '美团收银官网' },
                { label: '外卖配送加盟申请' },
                { label: '美团点评餐饮学院' },
                { label: '酒店商家入驻' },
                { label: '境内度假商家入驻' },
                { label: '综合商家入驻' },
                { label: '美团民宿房东商家入驻' },
                { label: '商家开票申请' },
                { label: '美团点评智能收银机' },
                { label: '美团点评餐饮开放平台' },
                { label: '美团点评收单' },
                { label: '免费试用美团排队' },
                { label: '快驴进货商家合作' },
                { label: '美团闪购商家入驻' }
              ]
            }
          ]
        },
        {
          linkList: [
            {
              title: '代理商加盟',
              subLinkList: [
                { label: '美团外卖代理商招募' },
                { label: '到店餐饮代理商招募' },
                { label: '非餐饮代理商招募' },
                { label: '美团联盟' },
                { label: '美团收银招募线上分销商' },
                { label: '美团点评5S服务商招募' },
                { label: '美团收单渠道代理商招募' }
              ]
            },
            {
              title: '美团规则',
              subLinkList: [
                { label: '规则中心' },
                { label: '规则目录' },
                { label: '规则评议院' }
              ]
            }
          ]
        },
        {
          linkList: [
            {
              title: '关注美团',
              subLinkList: [
                { label: '美团新浪微博' }
              ]
            },
            {
              title: '公司信息',
              subLinkList: [
                { label: '关于我们' },
                { label: '投资者关系' },
                { label: '加入我们' },
                { label: '商户诚信公约及管理办法' },
                { label: '保险经纪资质' }
              ]
            },
            {
              title: '廉正举报',
              subLinkList: [
                { label: '廉正举报平台' }
              ]
            },
            {
              title: '知识产权',
              subLinkList: [
                { label: '知识产权维权平台' }
              ]
            }
          ]
        },
        {
          linkList: [
            {
              title: '消费者服务热线',
              subLinkList: [
                { label: '外卖消费者：', value: '10109777' },
                { label: '猫眼消费者：', value: '10105335' },
                { label: '其他消费者：', value: '10107888' }
              ]
            },
            {
              title: '商家服务热线',
              subLinkList: [
                { label: '外卖&餐饮商家：', value: '10105557' },
                { label: '休闲娱乐、丽人、ktv、教育、结婚、亲子、家装等商家：', value: '10100107' }
              ]
            },
            {
              title: '投诉举报专区',
              subLinkList: [
                { label: '违法和不良信息举报电话：', value: '4006018900' },
                { label: '举报邮箱：', value: 'tousujubao@meituan.com' },
                { label: '网上有害信息举报' }
              ]
            },
            {
              title: '商家自助入驻美团入口',
              path: '/'
            },
            {
              title: '供应商注册入口',
              path: '/'
            }
          ]
        }
      ],
      copyrightList: [
        {
          linkList: [
            { label: '©美团网团购 meituan.com' },
            { label: '京ICP证070791号', path: '/' },
            { label: '京ICP备10211739号', path: '/' }
          ]
        },
        {
          linkList: [
            { label: '广播电视节目制作经营许可证（京）字第03889号', path: '/' }
          ]
        },
        {
          linkList: [
            { label: '食品经营许可证', path: '/' },
            { label: '互联网药品信息服务资格证', path: '/' }
          ]
        },
        {
          linkList: [
            { label: '医疗器械网络交易服务第三方平台备案：（京）网械平台备字[2018]第00004号', path: '/' }
          ]
        }
      ]
    }
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

.com-footer {
  margin-top: 40px;
  background: #f8f8f8;
  .footer-content {
    box-sizing: border-box;
    width: 1190px;
    margin: 0 auto;
    line-height: 2;
    font-size: 12px;
    color: #333;
    text-align: left;
    .footer-link {
      padding: 40px 45px;
      border-top: 1px solid $border-color-base;
      border-bottom: 1px solid $border-color-base;
      .footer-column {
        float: left;
        width: 20%;
        dl {
          padding-bottom: 20px;
          color: $color-text-regular;
          dt {
            color: #333;
            font-size: 14px;
            font-weight: 500;
          }
          a {
            color: $color-text-regular;
            &:hover {
              color: #fe8c00;
            }
          }
        }
      }
    }
    .footer-copyright {
      padding: 15px 0 30px 20px;
      line-height: 1.6;
      color: $color-text-secondary;
      &-left {
        float: left;
        a {
          margin-right: 20px;
        }
      }
      &-right {
        float: right;
        text-align: right;
      }
      &-cert {
        padding-top: 6px;
        text-align: left;
        .bus-license {
          img {
            float: left;
            width: 38px;
            height: 38px;
          }
          p {
            float: left;
            padding: 0 5px;
            line-height: 38px;
          }
        }
        a.sp-ft {
          display: inline-block;
          margin-right: 2px;
          height: 38px;
          background-image: url(https://s0.meituan.net/bs/fe-web-meituan/8a39c6b/img/sprites/footer.png);
          background-repeat: no-repeat;
          overflow: hidden;
          text-indent: -1000px;
        }
        .sp-ft--record {
          width: 109px;
          background-position: 0 -167px;
        }
        .sp-ft--knet {
          width: 107px;
          background-position: 0 -127px;
        }
        .sp-ft--12315 {
          width: 107px;
          background-position: 0 -40px;
        }
      }
    }
  }
}
</style>
