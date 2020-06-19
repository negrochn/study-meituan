<template>
  <div class="left-banner">
    <div class="category-nav-container">
      <div class="category-nav-title-wrapper">
        <span class="category-nav-title">全部分类</span>
        <span class="title-icon" />
      </div>
      <div class="category-nav-content-wrapper">
        <ul @mousemove="onMouseMove" @mouseenter="onMouseEnter" @mouseleave="onMouseLeave">
          <li v-for="item in navList" :key="item.id" class="nav-li">
            <i :class="`iconfontNew hc-icon-${item.id}`" />
            <span class="nav-text-wrapper">
              <span v-for="(itm, idx) in item.types" :key="itm.label">
                <nuxt-link :to="itm.path" class="nav-text">
                  <span>{{ itm.label }}</span>
                  <span v-if="itm.promotion" class="nav-promotion">
                    {{ itm.promotion }}
                  </span>
                </nuxt-link>
                <span v-if="idx !== item.types.length - 1"> / </span>
              </span>
            </span>
            <i class="nav-right-arrow" />
          </li>
        </ul>
      </div>
      <div v-show="isDetailShow" class="category-nav-detail-wrapper" @mouseenter="onMouseEnter" @mouseleave="onMouseLeave">
        <div class="category-nav-detail">
          <div v-for="item in detailList" :key="item.label" class="detail-area">
            <div class="detail-title-wrapper clearfix">
              <h2>
                <nuxt-link :to="item.path" class="detail-title">
                  {{ item.label }}
                </nuxt-link>
              </h2>
              <nuxt-link :to="item.path" class="detail-more">
                更多
                <i class="detail-right-arrow" />
              </nuxt-link>
            </div>
            <div class="detail-content">
              <nuxt-link v-for="itm in item.types" :key="itm.label" :to="itm.path" class="detail-text">
                {{ itm.label }}
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import _ from 'lodash'

const debounced = _.debounce(function (e) {
  const pageY = e.pageY
  const diffY = 208
  const height = 26
  const index = Math.floor((pageY - diffY) / height)
  this.curNav = index > -1 ? this.navList[index].id : ''
}, 50, {
  leading: false,
  trailing: true
})

export default {
  name: 'LeftBanner',
  data () {
    return {
      navList: [
        {
          id: 'foodNew',
          types: [
            {
              label: '美食',
              path: '/meishi'
            }
          ],
          subNavList: [
            {
              label: '美食',
              path: '/path',
              types: [
                { label: '代金券', path: '/meishi/c393' },
                { label: '甜点饮品', path: '/meishi/c11' },
                { label: '火锅', path: '/meishi/c17' },
                { label: '自助餐', path: '/meishi/c40' },
                { label: '小吃快餐', path: '/meishi/c36' },
                { label: '日韩料理', path: '/meishi/c28' },
                { label: '西餐', path: '/meishi/c35' },
                { label: '聚餐宴请', path: '/meishi/c395' },
                { label: '烧烤烤肉', path: '/meishi/c54' },
                { label: '东北菜', path: '/meishi/c20003' },
                { label: '川湘菜', path: '/meishi/c55' },
                { label: '江浙菜', path: '/meishi/c56' },
                { label: '香锅烤鱼', path: '/meishi/c20004' },
                { label: '粤港菜', path: '/meishi/c57' },
                { label: '中式烧烤/烤串', path: '/meishi/c400' },
                { label: '西北菜', path: '/meishi/c58' },
                { label: '咖啡酒吧茶馆', path: '/meishi/c41' },
                { label: '云贵菜', path: '/meishi/c60' },
                { label: '东南亚菜', path: '/meishi/c62' },
                { label: '海鲜', path: '/meishi/c63' },
                { label: '素食', path: '/meishi/c217' },
                { label: '台湾/客家菜', path: '/meishi/c227' },
                { label: '创意菜', path: '/meishi/c228' },
                { label: '汤/粥/炖菜', path: '/meishi/c229' },
                { label: '蒙餐', path: '/meishi/c232' },
                { label: '新疆菜', path: '/meishi/c233' },
                { label: '其他美食', path: '/meishi/c24' },
                { label: '京菜鲁菜', path: '/meishi/c59' }
              ]
            }
          ]
        },
        {
          id: 'waimaiNew',
          types: [
            {
              label: '外卖',
              path: '/waimai'
            }
          ],
          subNavList: [
            {
              label: '外卖',
              path: '/waimai',
              types: [
                { label: '美团外卖', path: '/waimai' }
              ]
            }
          ]
        },
        {
          id: 'hotelNew',
          types: [
            {
              label: '酒店',
              path: '/hotel',
              promotion: 'HOT'
            }
          ],
          subNavList: [
            {
              label: '酒店星级',
              path: '/hotel',
              types: [
                { label: '经济型', path: '/hotel/xj6' },
                { label: '舒适/三星', path: '/hotel/xj45' },
                { label: '高档/四星', path: '/hotel/xj23' },
                { label: '豪华/五星', path: '/hotel/xj01' }
              ]
            }
          ]
        },
        {
          id: 'zhenguoNew',
          types: [
            {
              label: '民宿',
              path: '/minsu'
            }
          ],
          subNavList: [
            {
              label: '热门城市',
              path: '/minsu',
              types: [
                { label: '上海', path: '/minsu/shanghai' },
                { label: '成都', path: '/minsu/chengdu' },
                { label: '北京', path: '/minsu/beijing' },
                { label: '重庆', path: '/minsu/chongqing' },
                { label: '南京', path: '/minsu/nanjing' },
                { label: '杭州', path: '/minsu/hangzhou' },
                { label: '广州', path: '/minsu/guangzhou' },
                { label: '西安', path: '/minsu/xian' },
                { label: '武汉', path: '/minsu/wuhan' },
                { label: '厦门', path: '/minsu/xiamen' },
                { label: '长沙', path: '/minsu/changsha' },
                { label: '青岛', path: '/minsu/qingdao' },
                { label: '深圳', path: '/minsu/shenzhen' },
                { label: '天津', path: '/minsu/tianjin' },
                { label: '苏州', path: '/minsu/suzhou' }
              ]
            },
            {
              label: '热门房源',
              path: '/minsu',
              types: [
                { label: '复式Loft', path: '/minsu' },
                { label: '别墅', path: '/minsu' }
              ]
            }
          ]
        },
        {
          id: 'maoyanNew',
          types: [
            { label: '猫眼电影', path: '/maoyan' }
          ],
          subNavList: [
            {
              label: '热门影院',
              path: '/maoyan/cinemas',
              types: [
                { label: '万达影城', path: '/maoyan/cshop/1703749' },
                { label: '横店电影城', path: '/maoyan/cshop/1438844' },
                { label: '中影国际影城', path: '/maoyan/cshop/2436061' },
                { label: '大地影院', path: '/maoyan/cshop/701599' },
                { label: '金逸影城', path: '/maoyan/cshop/90182909' },
                { label: '星美国际影城', path: '/maoyan/cshop/4701639' },
                { label: '百老汇影城', path: '/maoyan/cshop/1548060' },
                { label: '博纳国际影城', path: '/maoyan/cshop/179208751' },
                { label: 'SFC上影影城', path: '/maoyan/cshop/90293' },
                { label: '比高电影城', path: '/maoyan/cshop/1438344' }
              ]
            }
          ]
        },
        {
          id: 'planeNew',
          types: [
            { label: '机票', path: '/flight' },
            { label: '火车票', path: '/train' }
          ],
          subNavList: [
            {
              label: '机票',
              path: '/flight',
              types: [
                { label: '国内机票', path: '/flight' },
                { label: '国际/港澳台机票', path: '/iflight' }
              ]
            },
            {
              label: '火车票',
              path: '/train',
              types: [
                { label: '火车票', path: '/train' }
              ]
            }
          ]
        },
        {
          id: 'ktvNew',
          types: [
            { label: '休闲娱乐', path: '/xiuxianyule' },
            { label: 'KTV', path: '/xiuxianyule/c10' }
          ],
          subNavList: [
            {
              label: '休闲娱乐',
              path: '/xiuxianyule',
              types: [
                { label: '足疗按摩', path: '/xiuxianyule/c52' },
                { label: '洗浴/汗蒸', path: '/xiuxianyule/c112' },
                { label: '酒吧', path: '/xiuxianyule/c234' },
                { label: '密室逃脱', path: '/xiuxianyule/c230' },
                { label: '轰趴馆', path: '/xiuxianyule/c20773' },
                { label: '茶馆', path: '/xiuxianyule/c20772' },
                { label: '私人影院', path: '/xiuxianyule/c20104' },
                { label: 'DIY手工坊', path: '/xiuxianyule/c218' },
                { label: '采摘/农家乐', path: '/xiuxianyule/c516' },
                { label: '网吧网咖', path: '/xiuxianyule/c20770' },
                { label: '游乐游艺', path: '/xiuxianyule/c38' },
                { label: 'VR', path: '/xiuxianyule/c20779' },
                { label: '桌面游戏', path: '/xiuxianyule/c20777' },
                { label: '真人CS', path: '/xiuxianyule/c219' },
                { label: '棋牌室', path: '/xiuxianyule/c20776' },
                { label: '其他玩乐', path: '/xiuxianyule/c26' }
              ]
            },
            {
              label: 'KTV',
              path: '/xiuxianyule/c10',
              types: [
                { label: 'KTV', path: '/xiuxianyule/c10' }
              ]
            }
          ]
        },
        {
          id: 'lifeNew',
          types: [
            { label: '生活服务', path: '/shenghuo' }
          ],
          subNavList: [
            {
              label: '生活服务',
              path: '/shenghuo',
              types: [
                { label: '衣物/皮具洗护', path: '/shenghuo/c20112' },
                { label: '家政', path: '/shenghuo/c20113' },
                { label: '搬家运输', path: '/shenghuo/c20454' },
                { label: '送水', path: '/shenghuo/c20453' },
                { label: '充值缴费', path: '/shenghuo/c20111' },
                { label: '服饰/鞋包养护', path: '/shenghuo/c20057' },
                { label: '开锁换锁', path: '/shenghuo/c20457' },
                { label: '居家维修', path: '/shenghuo/c20474' },
                { label: '管道疏通', path: '/shenghuo/c20456' },
                { label: '家电维修清洗', path: '/shenghuo/c20459' },
                { label: '电脑维修', path: '/shenghuo/c20458' },
                { label: '手机维修', path: '/shenghuo/c20460' },
                { label: '证件照/肖像摄影', path: '/shenghuo/c20196' },
                { label: '照片冲印/图文文印', path: '/shenghuo/c221' },
                { label: '商务服务/法律服务', path: '/shenghuo/c21006' },
                { label: '文化传媒机构', path: '/shenghuo/c21007' },
                { label: '成人用品/情趣用品', path: '/shenghuo/c21113' }
              ]
            }
          ]
        },
        {
          id: 'beautyNew',
          types: [
            { label: '丽人', path: '/jiankangliren' },
            { label: '美发', path: '/jiankangliren/c74' },
            { label: '医学美容', path: '/jiankangliren/c20423' }
          ],
          subNavList: [
            {
              label: '丽人',
              path: '/jiankangliren',
              types: [
                { label: '美发', path: '/jiankangliren/c74' },
                { label: '美甲美睫', path: '/jiankangliren/c75' },
                { label: '美容美体', path: '/jiankangliren/c76' },
                { label: '医学美容', path: '/jiankangliren/c20423' },
                { label: '瑜伽舞蹈', path: '/jiankangliren/c220' },
                { label: '瘦身纤体', path: '/jiankangliren/c20422' },
                { label: '韩式定妆', path: '/jiankangliren/c20419' },
                { label: '祛痘', path: '/jiankangliren/c20421' },
                { label: '纹身', path: '/jiankangliren/c20420' },
                { label: '化妆品', path: '/jiankangliren/c20418' },
                { label: '养发', path: '/jiankangliren/c21394' }
              ]
            }
          ]
        },
        {
          id: 'marriedNew',
          types: [
            { label: '结婚', path: '/jiehun' },
            { label: '婚纱摄影', path: '/jiehun/c20198' },
            { label: '婚宴', path: '/jiehun/c20210' }
          ],
          subNavList: [
            {
              label: '结婚',
              path: '/jiehun',
              types: [
                { label: '婚纱摄影', path: '/jiehun/c20198' },
                { label: '旅拍', path: '/jiehun/c20303' },
                { label: '个性写真', path: '/jiehun/c20641' },
                { label: '婚宴', path: '/jiehun/c20210' },
                { label: '婚庆公司', path: '/jiehun/c20201' },
                { label: '婚纱礼服', path: '/jiehun/c20199' },
                { label: '西服定制', path: '/jiehun/c20200' },
                { label: '婚戒首饰', path: '/jiehun/c20202' },
                { label: '婚车租赁', path: '/jiehun/c20204' },
                { label: '司仪主持', path: '/jiehun/c20206' },
                { label: '彩妆造型', path: '/jiehun/c20205' },
                { label: '婚礼跟拍', path: '/jiehun/c20207' },
                { label: '婚礼小礼品', path: '/jiehun/c20203' },
                { label: '更多婚礼服务', path: '/jiehun/c20208' }
              ]
            }
          ]
        },
        {
          id: 'childNew',
          types: [
            { label: '亲子', path: '/qinzi' },
            { label: '儿童乐园', path: '/qinzi/c20108' },
            { label: '幼教', path: '/qinzi/c20045' }
          ],
          subNavList: [
            {
              label: '儿童乐园',
              path: '/qinzi/c20108',
              types: [
                { label: '婴儿游泳', path: '/qinzi/c20514' },
                { label: '其它亲子游乐', path: '/qinzi/c20782' }
              ]
            },
            {
              label: '幼儿教育',
              path: '/qinzi/c20045',
              types: [
                { label: '早教中心', path: '/qinzi/c20865' },
                { label: '少儿英语', path: '/qinzi/c20787' },
                { label: '智力开发', path: '/qinzi/c20789' },
                { label: '托班/幼儿园', path: '/qinzi/c20790' },
                { label: '幼儿教育', path: '/qinzi/c20864' },
                { label: '其他幼儿教育', path: '/qinzi/c20791' }
              ]
            },
            {
              label: '亲子摄影',
              path: '/qinzi/c398',
              types: [
                { label: '儿童摄影', path: '/qinzi/c20048' },
                { label: '孕妇写真', path: '/qinzi/c20515' },
                { label: '上门拍', path: '/qinzi/c20783' },
                { label: '其他亲子摄影', path: '/qinzi/c20784' }
              ]
            },
            {
              label: '孕产护理',
              path: '/qinzi/c20042',
              types: [
                { label: '月子会所', path: '/qinzi/c20516' },
                { label: '产后恢复', path: '/qinzi/c20792' },
                { label: '妇幼医院', path: '/qinzi/c20793' },
                { label: '孕产用品', path: '/qinzi/c20794' },
                { label: '开奶催乳', path: '/qinzi/c20795' },
                { label: '月嫂', path: '/qinzi/c20796' },
                { label: '亲子购物', path: '/qinzi/c20170' },
                { label: '宝宝派对', path: '/qinzi/c20785' },
                { label: '亲子服务', path: '/qinzi/c20171' }
              ]
            }
          ]
        },
        {
          id: 'sportNew',
          types: [
            { label: '运动健身', path: '/youyongjianshen' },
            { label: '健身中心', path: '/youyongjianshen/c20253' }
          ],
          subNavList: [
            {
              label: '运动健身',
              path: '/youyongjianshen',
              types: [
                { label: '健身中心', path: '/youyongjianshen/c20253' },
                { label: '武术场馆', path: '/youyongjianshen/c20266' },
                { label: '游泳馆', path: '/youyongjianshen/c20256' },
                { label: '羽毛球馆', path: '/youyongjianshen/c20257' },
                { label: '溜冰场', path: '/youyongjianshen/c20268' },
                { label: '射箭馆', path: '/youyongjianshen/c20270' },
                { label: '篮球场', path: '/youyongjianshen/c20258' },
                { label: '网球馆', path: '/youyongjianshen/c20259' },
                { label: '台球馆', path: '/youyongjianshen/c20262' },
                { label: '乒乓球', path: '/youyongjianshen/c20265' },
                { label: '足球场', path: '/youyongjianshen/c20264' },
                { label: '高尔夫场', path: '/youyongjianshen/c20260' },
                { label: '保龄球馆', path: '/youyongjianshen/c20261' },
                { label: '体育场馆', path: '/youyongjianshen/c20263' },
                { label: '马术场', path: '/youyongjianshen/c20267' },
                { label: '壁球馆', path: '/youyongjianshen/c20269' },
                { label: '更多运动', path: '/youyongjianshen/c20271' }
              ]
            }
          ]
        },
        {
          id: 'decorateNew',
          types: [
            { label: '家装', path: '/jiazhuang' },
            { label: '建材', path: '/jiazhuang/c20182' },
            { label: '家居', path: '/jiazhuang/c20771' }
          ],
          subNavList: [
            {
              label: '装修设计',
              path: '/jiazhuang/c20180',
              types: [
                { label: '半包装修', path: '/jiazhuang/c20878' },
                { label: '全包装修', path: '/jiazhuang/c20879' },
                { label: '清包装修', path: '/jiazhuang/c20880' }
              ]
            },
            {
              label: '装修建材',
              path: '/jiazhuang/c20182',
              types: [
                { label: '地板', path: '/jiazhuang/c20829' },
                { label: '瓷砖石材', path: '/jiazhuang/c20823' },
                { label: '橱柜', path: '/jiazhuang/c20825' },
                { label: '灯饰照明', path: '/jiazhuang/c20835' },
                { label: '厨卫洁具', path: '/jiazhuang/c20826' },
                { label: '油漆涂料', path: '/jiazhuang/c20822' },
                { label: '集成吊顶', path: '/jiazhuang/c20827' },
                { label: '墙纸墙艺', path: '/jiazhuang/c20824' },
                { label: '门窗', path: '/jiazhuang/c20832' },
                { label: '木材板材', path: '/jiazhuang/c20831' },
                { label: '家用五金', path: '/jiazhuang/c20828' },
                { label: '电工电料', path: '/jiazhuang/c20834' },
                { label: '楼梯', path: '/jiazhuang/c20830' },
                { label: '管材管件', path: '/jiazhuang/c20833' }
              ]
            },
            {
              label: '家具家居',
              path: '/jiazhuang/c20771',
              types: [
                { label: '家具', path: '/jiazhuang/c20838' },
                { label: '床上用品/家纺', path: '/jiazhuang/c20840' },
                { label: '家居饰品', path: '/jiazhuang/c20841' },
                { label: '厨具餐具', path: '/jiazhuang/c20839' },
                { label: '智能家居', path: '/jiazhuang/c20843' }
              ]
            },
            {
              label: '家装卖场',
              path: '/jiazhuang/c20184',
              types: [
                { label: '建材卖场', path: '/jiazhuang/c20847' },
                { label: '家居卖场', path: '/jiazhuang/c20846' },
                { label: '灯饰卖场', path: '/jiazhuang/c20845' }
              ]
            }
          ]
        },
        {
          id: 'educationNew',
          types: [
            { label: '学习培训', path: '/jiaoyupeixun' },
            { label: '音乐培训', path: '/xuexipeixun/c20287' }
          ],
          subNavList: [
            {
              label: '音乐培训',
              path: '/xuexipeixun/c20287',
              types: [
                { label: '钢琴', path: '/xuexipeixun/c20313' },
                { label: '吉他', path: '/xuexipeixun/c20314' },
                { label: '小提琴', path: '/xuexipeixun/c20315' },
                { label: '古筝', path: '/xuexipeixun/c20316' },
                { label: '架子鼓', path: '/xuexipeixun/c20317' },
                { label: '声乐', path: '/xuexipeixun/c20318' },
                { label: '其他音乐培训', path: '/xuexipeixun/c20319' }
              ]
            },
            {
              label: '职业技术',
              path: '/xuexipeixun/c20291',
              types: [
                { label: '美容化妆', path: '/xuexipeixun/c20323' },
                { label: '会计', path: '/xuexipeixun/c20324' },
                { label: 'IT', path: '/xuexipeixun/c20325' },
                { label: '厨艺', path: '/xuexipeixun/c20326' },
                { label: '管理培训', path: '/xuexipeixun/c20622' },
                { label: '摄影培训', path: '/xuexipeixun/c20623' },
                { label: '司法考试', path: '/xuexipeixun/c20624' },
                { label: '公务员培训', path: '/xuexipeixun/c20637' },
                { label: '其他职业培训', path: '/xuexipeixun/c20327' }
              ]
            },
            {
              label: '外语培训',
              path: '/xuexipeixun/c20286',
              types: [
                { label: '英语', path: '/xuexipeixun/c20306' },
                { label: '日语', path: '/xuexipeixun/c20307' },
                { label: '韩语', path: '/xuexipeixun/c20308' },
                { label: '法语', path: '/xuexipeixun/c20309' },
                { label: '德语', path: '/xuexipeixun/c20310' },
                { label: '汉语', path: '/xuexipeixun/c20311' },
                { label: '俄语', path: '/xuexipeixun/c20620' },
                { label: '西班牙语', path: '/xuexipeixun/c20621' },
                { label: '其他外语', path: '/xuexipeixun/c20312' }
              ]
            },
            {
              label: '美术培训',
              path: '/xuexipeixun/c20288',
              types: [
                { label: '绘画', path: '/xuexipeixun/c20320' },
                { label: '书法', path: '/xuexipeixun/c20321' },
                { label: '其他美术', path: '/xuexipeixun/c20322' }
              ]
            }
          ]
        },
        {
          id: 'medicalNew',
          types: [
            { label: '医疗健康', path: '/yiliao' },
            { label: '宠物', path: '/chongwu/c20691' },
            { label: '爱车', path: '/aiche' }
          ],
          subNavList: [
            {
              label: '医疗健康',
              path: '/yiliao',
              types: [
                { label: '医院', path: '/yiliao/c20275' },
                { label: '齿科口腔', path: '/yiliao/c20276' },
                { label: '体检中心', path: '/yiliao/c20277' },
                { label: '药店', path: '/yiliao/c20278' },
                { label: '中医', path: '/yiliao/c20279' },
                { label: '其他健康服务', path: '/yiliao/c20280' }
              ]
            },
            {
              label: '爱车',
              path: '/aiche',
              types: [
                { label: '洗车', path: '/aiche/c20115' },
                { label: '租车', path: '/aiche/c20116' },
                { label: '加油站', path: '/aiche/c20117' },
                { label: '维修保养', path: '/aiche/c20118' },
                { label: '驾校', path: '/aiche/c20119' },
                { label: '汽车美容', path: '/aiche/c20120' },
                { label: '陪练', path: '/aiche/c20121' },
                { label: '汽车用品', path: '/aiche/c20135' },
                { label: '停车场', path: '/aiche/c20161' },
                { label: '汽车保险', path: '/aiche/c20162' },
                { label: '4S店/汽车销售', path: '/aiche/c20163' },
                { label: '更多汽车服务', path: '/aiche/c20164' },
                { label: '机油保养', path: '/aiche/c20174' },
                { label: '汽车报价', path: '/aiche/c20172' },
                { label: '二手车', path: '/aiche/c20215' },
                { label: '广告驾校', path: '/aiche/c20237' },
                { label: '交警队', path: '/aiche/c20381' },
                { label: '汽车改装', path: '/aiche/c20767' },
                { label: '汽车配件', path: '/aiche/c20768' }
              ]
            },
            {
              label: '宠物',
              path: '/chongwu/c20691',
              types: [
                { label: '宠物店', path: '/chongwu/c25147' },
                { label: '宠物医院', path: '/chongwu/c25148' }
              ]
            }
          ]
        },
        {
          id: 'barNew',
          types: [
            { label: '酒吧', path: '/xiuxianyule/c234' },
            { label: '密室逃脱', path: '/xiuxianyule/c230' }
          ],
          subNavList: [
            {
              label: '玩乐',
              path: '/xiuxianyule',
              types: [
                { label: 'KTV', path: '/xiuxianyule/c10' },
                { label: '酒吧', path: '/xiuxianyule/c234' },
                { label: '密室逃脱', path: '/xiuxianyule/c230' },
                { label: '游乐游艺', path: '/xiuxianyule/c38' },
                { label: '网吧网咖', path: '/xiuxianyule/c20770' },
                { label: '私人影院', path: '/xiuxianyule/c20104' },
                { label: 'DIY手工坊', path: '/xiuxianyule/c218' },
                { label: '桌面游戏', path: '/xiuxianyule/c20777' },
                { label: '采摘/农家乐', path: '/xiuxianyule/c516' },
                { label: '棋牌室', path: '/xiuxianyule/c20776' },
                { label: '轰趴馆', path: '/xiuxianyule/c20773' },
                { label: '真人CS', path: '/xiuxianyule/c219' },
                { label: 'VR', path: '/xiuxianyule/c20779' },
                { label: '其他玩乐', path: '/xiuxianyule/c26' }
              ]
            }
          ]
        }
      ],
      curNav: '',
      timer: null
    }
  },
  computed: {
    isDetailShow () {
      return Boolean(this.curNav)
    },
    detailList () {
      return (this.navList.filter(item => item.id === this.curNav)[0] || {}).subNavList || []
    }
  },
  methods: {
    onMouseEnter () {
      clearTimeout(this.timer)
    },
    onMouseLeave () {
      debounced.cancel()
      this.timer = setTimeout(() => {
        this.curNav = ''
      }, 100)
    },
    onMouseMove: debounced
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.left-banner {
  float: left;
  .category-nav-container {
    position: relative;
    float: left;
    box-sizing: border-box;
    margin-top: -50px;
    width: 230px;
    height: 475px;
    background: $color-white;
    color: $color-text-regular - $color-text-span2;
    border: 1px solid $border-color-base;
    .category-nav-title-wrapper {
      box-sizing: border-box;
      padding-top: 15px;
      height: 50px;
      .category-nav-title {
        margin-left: 15px;
        color: $color-text-primary;
        font-size: 16px;
        font-weight: 700;
      }
    }
    .category-nav-content-wrapper {
      ul {
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding: 10px 0 8px;
        height: 425px;
      }
    }
    .category-nav-detail-wrapper {
      position: absolute;
      top: 60px;
      left: 230px;
      width: 400px;
      height: 416px;
      background: $color-white;
      color: $color-text-regular;
      overflow: hidden;
    }
    .nav-li {
      position: relative;
      box-sizing: border-box;
      padding: 2px 12px;
      height: 26px;
      &:hover {
        background: rgba(255, 150, 0, 0.08);
        color: $color-text-primary;
        a {
          font-weight: 700;
        }
        .nav-text {
          color: $color-text-primary;
        }
        .nav-right-arrow {
          color: $color-text-primary;
          border-bottom: 1px solid $color-text-primary;
          border-right: 1px solid $color-text-primary;
        }
        .nav-promotion {
          font-weight: 400;
          background: linear-gradient(to bottom right, #FFD000, #FFBD00);
        }
      }
      .nav-right-arrow {
        position: absolute;
        display: block;
        top: 0;
        bottom: 0;
        right: 13px;
        margin: auto;
        width: 4px;
        height: 4px;
        color: #BFBFBF;
        border-bottom: 1px solid #BFBFBF;
        border-right: 1px solid #BFBFBF;
        transform: rotate(-45deg);
      }
    }
    .nav-text-wrapper {
      display: inline-block;
      margin-left: 11px;
    }
    .iconfontNew:before {
      display: inline-block;
      width: 16px;
      height: 16px;
      font-size: 16px;
    }
    .nav-text {
      height: 20px;
      line-height: 20px;
      font-size: 13px;
      color: #646464;
      cursor: pointer;
    }
    .nav-promotion {
      position: relative;
      display: inline-block;
      margin-left: 5px;
      padding: 0 7px;
      background: #FFF3CC;
      font-size: 12px;
      color: $color-text-primary;
      border-radius: 10px;
      transform: scale(.9);
      opacity: 1;
    }
    .detail-area {
      padding: 0 30px;
      .detail-title-wrapper {
        margin-top: 24px;
        height: 22px;
        line-height: 22px;
        padding-bottom: 10px;
        border-bottom: 1px solid $border-color-base;
        .detail-title {
          float: left;
          font-size: 16px;
          font-weight: 500;
          color: $color-text-primary;
        }
        .detail-more {
          position: relative;
          float: right;
          margin-right: 6px;
          font-size: 12px;
          color: $color-text-secondary;
        }
        .detail-right-arrow {
          position: absolute;
          display: block;
          top: 0;
          bottom: 0;
          right: -6px;
          margin: auto;
          width: 4px;
          height: 4px;
          border-bottom: 1px solid #999;
          border-right: 1px solid #999;
          transform: rotate(-45deg);
        }
      }
      .detail-content {
        .detail-text {
          display: inline-block;
          margin-top: 10px;
          margin-right: 16px;
          line-height: 15px;
          font-size: 12px;
        }
      }
    }
  }
}
</style>
