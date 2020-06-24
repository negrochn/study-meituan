<template>
  <div class="zhenguo-container">
    <div style="background: linear-gradient(to right, rgb(243, 182, 74) 2%, rgb(242, 197, 69) 97%) rgb(243, 182, 74);" class="index-nav-container">
      <ul class="clearfix">
        <li class="title nav-item mf-shang-hei-regular">
          推荐民宿
        </li>
        <li v-for="item in minsuList" :key="item.cityId" :class="['nav-item', { 'active': curCity === item.city }]" @mouseenter="onMouseEnter">
          {{ item.city }}
        </li>
        <li class="total nav-item">
          <nuxt-link to="/minsu">
            <span>全部</span>
            <span class="right-arrow iconfont icon-btn_right" />
          </nuxt-link>
        </li>
      </ul>
    </div>
    <div class="minsu-ls-view clearfix">
      <div v-for="item in minsuList" :key="item.productId" :style="`display: ${curCity === item.city ? 'flex' : 'none'};`" class="products">
        <div v-for="product in item.productList" :key="product.productId" class="minsu-item">
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
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Zhenguo',
  data () {
    return {
      minsuList: [
        {
          city: '上海',
          cityId: 310100,
          productList: [
            {
              productId: '10488571',
              price: 328,
              hostAvatarUrl: null,
              title: '虹桥十分钟万达美食街地铁站（黑精灵）',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '虹桥枢纽',
              starRating: 50,
              commentNumber: 4,
              coverImage: 'http://p1.meituan.net/iphoenix/a23a7d9379a098529f509594bec9bef0123306.jpg',
              favCount: 65,
              poiId: '1408096868',
              dpPoiId: '1408096868'
            },
            {
              productId: '8065196',
              price: 258,
              hostAvatarUrl: null,
              title: '长寿路北欧风情主题民宿',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '长寿路',
              starRating: 47,
              commentNumber: 12,
              coverImage: 'https://img.meituan.net/phoenix/f09c64e5b74d20bce9cf866c321e7d4a160732.jpg',
              favCount: 130,
              poiId: '1167397657',
              dpPoiId: '1167397657'
            },
            {
              productId: '7072733',
              price: 98,
              hostAvatarUrl: null,
              title: '【光明屋2】近虹桥机场火车站，毗邻国家会展中心，凌空，13号线地铁直达南京路、淮海路、新天地等，万达广场、家乐福。',
              rentType: 1,
              layoutRoom: 4,
              maxGuestNumber: 1,
              locationArea: '虹桥枢纽',
              starRating: 45,
              commentNumber: null,
              coverImage: 'https://img.meituan.net/phoenix/66293abf4aeaa0b62720481b2eff2f02138438.jpg',
              favCount: 16,
              poiId: '1866277231',
              dpPoiId: '1866277231'
            },
            {
              productId: '8184096',
              price: 218,
              hostAvatarUrl: null,
              title: '独立空间 独栋公寓 家一般温馨',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '吴淞口国际游轮港',
              starRating: 48,
              commentNumber: 17,
              coverImage: 'https://img.meituan.net/phoenix/aec5e6143fd51a1c9241ff31b2adebc161452.jpg',
              favCount: 152,
              poiId: '990715644',
              dpPoiId: '990715644'
            },
            {
              productId: '8007195',
              price: 168,
              hostAvatarUrl: null,
              title: '茗沅.小舍 整套/大床房/近5号地铁/古华公园',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '奉贤开发区',
              starRating: 50,
              commentNumber: 5,
              coverImage: 'https://img.meituan.net/phoenix/17902beef0aaa5eb6b3b59c7f2bad956404237.jpg',
              favCount: 87,
              poiId: '621713744',
              dpPoiId: '621713744'
            },
            {
              productId: '7234843',
              price: 199,
              hostAvatarUrl: null,
              title: 'DSN【羽梦】双人床',
              rentType: 1,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '迪士尼度假区',
              starRating: 50,
              commentNumber: 2,
              coverImage: 'https://img.meituan.net/iphoenix/f8ed12be3bb11300f1238cfdb088358522461.jpg',
              favCount: 2,
              poiId: '194854805',
              dpPoiId: '131873859'
            }
          ]
        },
        {
          city: '南京',
          cityId: 320100,
          productList: [
            {
              productId: '11771704',
              price: 199,
              hostAvatarUrl: null,
              title: '无接触入住/简约景观大床房/高空夜景/巨幕投影/独立卫生间/近南京南/地铁直达夫子庙/新街口',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '建宁路',
              starRating: 45,
              commentNumber: null,
              coverImage: 'http://p0.meituan.net/iphoenix/24aa5be5beb3b7b851babf4b77b1ca9c2414543.jpg',
              favCount: 20,
              poiId: '1001113410',
              dpPoiId: '1001113410'
            },
            {
              productId: '8191517',
              price: 188,
              hostAvatarUrl: null,
              title: '【米修樱花】万达茂/仙林大学城/万达茂52平/南京大学/仙林湖地铁站300米//百寸4K巨幕投影',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '摄山',
              starRating: 47,
              commentNumber: 17,
              coverImage: 'http://p0.meituan.net/iphoenix/d0e56c94ab92c3b98e23711bb81a5b266241141.jpg',
              favCount: 1239,
              poiId: '675713406',
              dpPoiId: '675713406'
            },
            {
              productId: '9062502',
              price: 123,
              hostAvatarUrl: null,
              title: '24小时免费接送机/禄口机场/南京禄口国际机场/标准大床房/ins风/面积大',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: null,
              starRating: 49,
              commentNumber: 44,
              coverImage: 'http://p0.meituan.net/iphoenix/bd750e70a6073a8ae8ced3f4da332dc4912820.jpg',
              favCount: 246,
              poiId: '1666327530',
              dpPoiId: '1666327530'
            },
            {
              productId: '9080087',
              price: 88,
              hostAvatarUrl: null,
              title: '可短租月租 预定先咨询 平价房一室一厅长租优惠',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: null,
              starRating: 48,
              commentNumber: 8,
              coverImage: 'https://img.meituan.net/phoenix/2e493b32b726f09eea34a8e426802be91767744.jpg',
              favCount: 83,
              poiId: '1793635076',
              dpPoiId: '1793635076'
            },
            {
              productId: '7459182',
              price: 188,
              hostAvatarUrl: null,
              title: '【兔子洞-薇薇安城堡】45平仙女民宿，高清投影，独立卫浴，南京火车站，迈皋桥，燕子矶，火车站，迈皋桥，晓庄，新港，特教院',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: null,
              starRating: 48,
              commentNumber: 28,
              coverImage: 'https://img.meituan.net/phoenix/a2f5b9ff904db7b816f2e736fd816699634445.jpg',
              favCount: 185,
              poiId: '195126850',
              dpPoiId: '132140096'
            },
            {
              productId: '9051031',
              price: 98,
              hostAvatarUrl: null,
              title: '漫途—南京南站、百家湖1912、地铁3号线胜太西路站',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 1,
              locationArea: '胜太路沿线',
              starRating: 50,
              commentNumber: 34,
              coverImage: 'https://img.meituan.net/phoenix/abda2bfa1f3df1fcb6b5f71dbd7e7856814444.jpg',
              favCount: 332,
              poiId: '1109165842',
              dpPoiId: '1109165842'
            }
          ]
        },
        {
          city: '苏州',
          cityId: 320500,
          productList: [
            {
              productId: '8009678',
              price: 179,
              hostAvatarUrl: null,
              title: '近火车站/地铁站/拙政园/观前街/山塘街/平江路/虎丘/万达广场.精致大床。',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '江星商业广场',
              starRating: 49,
              commentNumber: 52,
              coverImage: 'https://img.meituan.net/phoenix/feedf3853b4bdce10e81f14ab622b910214236.jpg',
              favCount: 353,
              poiId: '1360754142',
              dpPoiId: '1360754142'
            },
            {
              productId: '1469168',
              price: 123,
              hostAvatarUrl: null,
              title: '普通大床房-蘇舍汉服主题民宿平江路观前街店',
              rentType: 1,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '观前街地区',
              starRating: 46,
              commentNumber: 299,
              coverImage: 'http://p0.meituan.net/iphoenix/8c4f96304521bfc89126569d144adb10318460.jpg',
              favCount: 3166,
              poiId: '164346500',
              dpPoiId: '97461897'
            },
            {
              productId: '10707340',
              price: 138,
              hostAvatarUrl: null,
              title: '地铁口 近同理古镇、临苏州湾   万科精装交付',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: null,
              starRating: 50,
              commentNumber: 3,
              coverImage: 'https://img.meituan.net/phoenix/49a7f303b2c29d157d41a0a291592aa12907717.jpg',
              favCount: 16,
              poiId: '653766643',
              dpPoiId: '653766643'
            },
            {
              productId: '7122364',
              price: 90,
              hostAvatarUrl: null,
              title: '『甘愿』市中心 情侣影院 临地铁口/火车站/平江路/观前街/拙政园/山塘街/苏州博物馆/狮子林等',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 3,
              locationArea: '三香路沿线',
              starRating: 46,
              commentNumber: 57,
              coverImage: 'https://img.meituan.net/phoenix/5412eeb3342e83a44b26e15dfb513dab120277.jpg',
              favCount: 1138,
              poiId: '193986271',
              dpPoiId: '131017055'
            },
            {
              productId: '8102936',
              price: 129,
              hostAvatarUrl: null,
              title: '近火车站/地铁站/拙政园/观前街/山塘街/平江路/虎丘/万达广场.精致大床。',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '江星商业广场',
              starRating: 46,
              commentNumber: 48,
              coverImage: 'https://img.meituan.net/phoenix/ad39110b511777eb643b94d94847998c136931.jpg',
              favCount: 295,
              poiId: '1566236386',
              dpPoiId: '1566236386'
            },
            {
              productId: '2934031',
              price: 238,
              hostAvatarUrl: null,
              title: '宿归：苏州湾轻奢风/湖景房+地铁口太湖畔+全品牌五星用品配置（地铁4号线近同里观前街/梦幻水世界/北外(不好可以打房东)',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: null,
              starRating: 49,
              commentNumber: 32,
              coverImage: 'http://p1.meituan.net/iphoenix/037998982b165874c3c185ac410104f955745.jpg',
              favCount: 251,
              poiId: '183981439',
              dpPoiId: '121483536'
            }
          ]
        },
        {
          city: '合肥',
          cityId: 340100,
          productList: [
            {
              productId: '1150627',
              price: 160,
              hostAvatarUrl: null,
              title: '宝利丰广场爱情公寓‖麋鹿情缘‖爱丽小屋',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '宁国路工大美食一条街',
              starRating: 48,
              commentNumber: 64,
              coverImage: 'https://img.meituan.net/iphoenix/35c4e07935b3fc71a8700c5892a84b2262691.jpg',
              favCount: 1310,
              poiId: '162125116',
              dpPoiId: '95330954'
            },
            {
              productId: '7466300',
              price: 50,
              hostAvatarUrl: null,
              title: '美梦公寓，交通便利，干净卫生，价格实惠，3号地铁口',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 1,
              locationArea: '合肥站/元一时代广场',
              starRating: 50,
              commentNumber: 2,
              coverImage: 'http://p0.meituan.net/iphoenix/de5f075534d977cde1416f05f5ed7779681539.jpg',
              favCount: 7,
              poiId: '781290123',
              dpPoiId: '781290123'
            },
            {
              productId: '9198941',
              price: 148,
              hostAvatarUrl: null,
              title: '栖悦民宿温馨一居/地铁一号线/滨湖会展中心',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '滨湖世纪城',
              starRating: 43,
              commentNumber: 8,
              coverImage: 'https://img.meituan.net/phoenix/cb60c1d5260f46a5eb3d07e2ff2afadc82571.jpg',
              favCount: 59,
              poiId: '1046000846',
              dpPoiId: '1046000846'
            },
            {
              productId: '10516285',
              price: 108,
              hostAvatarUrl: null,
              title: '逍遥津民宿来了',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '合肥站/元一时代广场',
              starRating: 50,
              commentNumber: 6,
              coverImage: 'https://img.meituan.net/phoenix/941d3985b261852f494cf46ca7f364952057844.jpg',
              favCount: 69,
              poiId: '566667232',
              dpPoiId: '566667232'
            },
            {
              productId: '10478415',
              price: 120,
              hostAvatarUrl: null,
              title: '【偶遇】中环城/亲密空间轻奢风/超大落地窗一居室/大学城/翡翠湖/海洋世界/明珠广场',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '明珠广场',
              starRating: 50,
              commentNumber: 6,
              coverImage: 'https://img.meituan.net/phoenix/c45a9744eb5bbb43c7c6e4c34e534d8a672894.jpg',
              favCount: 40,
              poiId: '1967506554',
              dpPoiId: '1967506554'
            },
            {
              productId: '10646359',
              price: 40,
              hostAvatarUrl: null,
              title: '中国科技大学赛博数码城附近黄金广场梦缘公寓新鲜出租！可日租/短租/长租',
              rentType: 1,
              layoutRoom: 8,
              maxGuestNumber: 1,
              locationArea: '长江中路商业区',
              starRating: 50,
              commentNumber: 7,
              coverImage: 'https://img.meituan.net/phoenix/f3916021a057f63a0eea852c0cb30de82956546.jpg',
              favCount: 69,
              poiId: '1254610093',
              dpPoiId: '1254610093'
            }
          ]
        },
        {
          city: '南昌',
          cityId: 360100,
          productList: [
            {
              productId: '2937399',
              price: 99,
              hostAvatarUrl: null,
              title: '【古风如故阁】地铁口天虹楼上，师大江科对面古色古香 还有古装 榻榻米喝茶聊天情调足',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '瑶湖',
              starRating: 49,
              commentNumber: 78,
              coverImage: 'https://img.meituan.net/phoenix/582a03ae1bfb54a36b77b5c84a2d376a57733.jpg',
              favCount: 426,
              poiId: '184177663',
              dpPoiId: '121684858'
            },
            {
              productId: '10509955',
              price: 238,
              hostAvatarUrl: null,
              title: '子曰 · 客栈  【木舍】影院房红谷滩万达广场 可做饭 地铁口',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '万达广场',
              starRating: 50,
              commentNumber: 9,
              coverImage: 'https://img.meituan.net/phoenix/496a235a4423f8116b8cfac9896ee7c3487016.jpg',
              favCount: 160,
              poiId: '1386780053',
              dpPoiId: '1386780053'
            },
            {
              productId: '10681156',
              price: 218,
              hostAvatarUrl: null,
              title: '【墅栖·梦之蓝】地铁口·榻榻米·巨幕高清影院',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '前湖大学城',
              starRating: 48,
              commentNumber: 10,
              coverImage: 'https://img.meituan.net/phoenix/aa663d046ef39050e0c418cb4821861d395253.jpg',
              favCount: 149,
              poiId: '621328725',
              dpPoiId: '621328725'
            },
            {
              productId: '8197409',
              price: 109,
              hostAvatarUrl: null,
              title: '红谷滩欧尚公寓/温馨大床房 语枫',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: null,
              starRating: 50,
              commentNumber: 1,
              coverImage: 'https://img.meituan.net/iphoenix/e693c81ab88397d3f2c27c0e54ccbe2e52799.jpg',
              favCount: 19,
              poiId: '1758515294',
              dpPoiId: '1758515294'
            },
            {
              productId: '10529864',
              price: 148,
              hostAvatarUrl: null,
              title: '南昌西站/时尚大床房/LOFT公寓',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '南昌西站',
              starRating: 47,
              commentNumber: 17,
              coverImage: 'https://img.meituan.net/phoenix/d6143cd0c906719f22abf03d8f303726149039.jpg',
              favCount: 182,
              poiId: '1149279431',
              dpPoiId: '1149279431'
            },
            {
              productId: '9198971',
              price: 99,
              hostAvatarUrl: null,
              title: '『心 舍』波西米亚梦幻风／乐盈广场／昌北大学城／紫荆夜市',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '下罗',
              starRating: 49,
              commentNumber: 115,
              coverImage: 'https://img.meituan.net/phoenix/1f928675c4ba67104ade2b6c55fe2ac7528636.jpg',
              favCount: 412,
              poiId: '1310240833',
              dpPoiId: '1310240833'
            }
          ]
        },
        {
          city: '宁波',
          cityId: 330200,
          productList: [
            {
              productId: '7186879',
              price: 100,
              hostAvatarUrl: null,
              title: '近高铁机场.客运中心 大床新居【壹舍】4',
              rentType: 1,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '海曙商业区',
              starRating: 50,
              commentNumber: 8,
              coverImage: 'https://img.meituan.net/phoenix/59f78e95647abbf3ed75ed37ec954f2f534523.jpg',
              favCount: 110,
              poiId: '195072803',
              dpPoiId: '132088257'
            },
            {
              productId: '7272187',
              price: 178,
              hostAvatarUrl: null,
              title: '【布拉琪】天一广场旁/百寸投影仪/拍照好地/白法式轻奢主义',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '海曙商业区',
              starRating: 45,
              commentNumber: 30,
              coverImage: 'http://p0.meituan.net/iphoenix/f04e728e3f5048374d078a50c70532804464571.jpg',
              favCount: 683,
              poiId: '193816195',
              dpPoiId: '130847452'
            },
            {
              productId: '10552054',
              price: 178,
              hostAvatarUrl: null,
              title: '『初见逸居』外事学校 \\恒一广场旁\\直达南塘老街\\鼓楼\\天一广场\\可做饭\\投影\\小屋位于客运中心',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '鄞州商业区',
              starRating: 50,
              commentNumber: 20,
              coverImage: 'https://img.meituan.net/phoenix/0009cbb109486f08935a4cb2f07ae3a23721788.jpg',
              favCount: 258,
              poiId: '1648861723',
              dpPoiId: '1648861723'
            },
            {
              productId: '7462589',
              price: 258,
              hostAvatarUrl: null,
              title: '《寄居蟹庭院后花园房》市中心！走路两分钟到老外滩/紧邻天一/城隍庙/鼓楼/商业核心圈/可做饭',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '老外滩商业区',
              starRating: 48,
              commentNumber: 20,
              coverImage: 'https://img.meituan.net/phoenix/87e600fc8978dd5b62b95733c297f9f6833380.jpg',
              favCount: 517,
              poiId: '195203615',
              dpPoiId: '132214775'
            },
            {
              productId: '11721738',
              price: 219,
              hostAvatarUrl: null,
              title: '【七只猫·清白之年】 100寸投影/可做饭/ 拍照 /落地窗夜景/鄞州万达 /罗蒙乐园',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '鄞州大学城/万达广场商业区',
              starRating: 50,
              commentNumber: 1,
              coverImage: 'http://p0.meituan.net/iphoenix/f0c6bf32024f47e3de12bd88754d17302794929.jpg',
              favCount: 19,
              poiId: '1738303666',
              dpPoiId: '1738303666'
            },
            {
              productId: '11573305',
              price: 168,
              hostAvatarUrl: null,
              title: '【初见逸居】外事学校 \\恒一广场旁\\直达南塘老街\\鼓楼\\天一广场\\可做饭\\投影\\小屋位于客运中心',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '鄞州商业区',
              starRating: 50,
              commentNumber: 6,
              coverImage: 'https://img.meituan.net/phoenix/200f59419b5cf51a58d27330113a75a42600994.jpg',
              favCount: 55,
              poiId: '765449416',
              dpPoiId: '765449416'
            }
          ]
        },
        {
          city: '福州',
          cityId: 350100,
          productList: [
            {
              productId: '11669334',
              price: 158,
              hostAvatarUrl: null,
              title: '福州南站ins风轻奢舒适双床房',
              rentType: 0,
              layoutRoom: 2,
              maxGuestNumber: 4,
              locationArea: '火车南站',
              starRating: 45,
              commentNumber: null,
              coverImage: 'https://img.meituan.net/phoenix/9f094ac829ff9fb819da3bc4d27bc0172938534.jpg',
              favCount: 6,
              poiId: '1434600195',
              dpPoiId: '1434600195'
            },
            {
              productId: '10548734',
              price: 188,
              hostAvatarUrl: null,
              title: '福州火车南站温馨舒适ins公寓民宿',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 3,
              locationArea: '火车南站',
              starRating: 50,
              commentNumber: 10,
              coverImage: 'https://img.meituan.net/phoenix/3472514dd67c36fee86f3a68e69f78c02030477.jpg',
              favCount: 47,
              poiId: '677252519',
              dpPoiId: '677252519'
            },
            {
              productId: '10624455',
              price: 208,
              hostAvatarUrl: null,
              title: '达道地铁口 上下杭 宝龙 中亭街 三坊七巷 高层现代风 百寸高清投影 整套公寓 新房特惠',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '时代名城/文化宫',
              starRating: 48,
              commentNumber: 12,
              coverImage: 'https://img.meituan.net/phoenix/68304af494db3b1b5b589628abb16649224874.jpg',
              favCount: 108,
              poiId: '525317699',
              dpPoiId: '525317699'
            },
            {
              productId: '2721566',
              price: 118,
              hostAvatarUrl: null,
              title: '博仕后天小鹅爱情主题房',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '福州大学城',
              starRating: 50,
              commentNumber: 5,
              coverImage: 'https://img.meituan.net/iphoenix/83b59f4c1b4788f61cda2b7a5bbb8ae292543.jpg',
              favCount: 131,
              poiId: '174856395',
              dpPoiId: '107700136'
            },
            {
              productId: '10789872',
              price: 99,
              hostAvatarUrl: null,
              title: '『一舍』民宿 繁心 永嘉天地',
              rentType: 1,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '福州大学城',
              starRating: 45,
              commentNumber: null,
              coverImage: 'https://img.meituan.net/phoenix/665aa16de1ea35f555c63f88647ca713727759.jpg',
              favCount: 43,
              poiId: '1143981578',
              dpPoiId: '1143981578'
            },
            {
              productId: '8284663',
              price: 198,
              hostAvatarUrl: null,
              title: '上下杭环面阳光清新房/近中亭街宝龙/近地铁',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '时代名城/文化宫',
              starRating: 47,
              commentNumber: 3,
              coverImage: 'https://img.meituan.net/phoenix/30a22945aa46aab32ea44c46c21def75999856.jpg',
              favCount: 114,
              poiId: '1678415696',
              dpPoiId: '1678415696'
            }
          ]
        },
        {
          city: '无锡',
          cityId: 320200,
          productList: [
            {
              productId: '10689092',
              price: 80,
              hostAvatarUrl: null,
              title: '雪溪苑简约欧式1.8米大床房/恒华科技园旁边/融创乐园/华莱坞影视基地/设施齐全/交通方便',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '无锡太湖风景区',
              starRating: 50,
              commentNumber: 3,
              coverImage: 'http://p1.meituan.net/iphoenix/1b2560471381e0edb0fb38ccec60d11c715047.jpg',
              favCount: 46,
              poiId: '502229807',
              dpPoiId: '502229807'
            },
            {
              productId: '9182663',
              price: 229,
              hostAvatarUrl: null,
              title: 'Ag灰调  临融创茂、江南大学、三国城、雪浪山',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '无锡太湖风景区',
              starRating: 50,
              commentNumber: 6,
              coverImage: 'https://img.meituan.net/phoenix/1e0dd56bdef6ea43a3435955df3deaa3739540.jpg',
              favCount: 129,
              poiId: '642111505',
              dpPoiId: '642111505'
            },
            {
              productId: '10631149',
              price: 138,
              hostAvatarUrl: null,
              title: '【听雨民宿】红星大都汇超现代一居',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '无锡太湖风景区',
              starRating: 50,
              commentNumber: 10,
              coverImage: 'https://img.meituan.net/phoenix/077adc10aa4ced60c78ec146d2cd5420669762.jpg',
              favCount: 62,
              poiId: '1866511100',
              dpPoiId: '1866511100'
            },
            {
              productId: '10676126',
              price: 75,
              hostAvatarUrl: null,
              title: '简约大床房/设施齐全/性价比高',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '工业园区',
              starRating: 45,
              commentNumber: 23,
              coverImage: 'http://p0.meituan.net/iphoenix/fff7ddde154a734eed234a5ecbace0541082821.jpg',
              favCount: 168,
              poiId: '1540307230',
              dpPoiId: '1540307230'
            },
            {
              productId: '8688584',
              price: 168,
              hostAvatarUrl: null,
              title: '【半糖主义】近酒吧街 地铁站 火车站旁 巨幕投影',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '南禅寺/中山路/南长街',
              starRating: 48,
              commentNumber: 24,
              coverImage: 'https://img.meituan.net/phoenix/17e9096cf9e86af848b0fd451f351cfc743545.jpg',
              favCount: 278,
              poiId: '857879279',
              dpPoiId: '857879279'
            },
            {
              productId: '8824133',
              price: 159,
              hostAvatarUrl: null,
              title: '【海盐】投影美居｜一号线｜江南大学｜长广溪｜文旅城',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '无锡太湖风景区',
              starRating: 46,
              commentNumber: 12,
              coverImage: 'https://img.meituan.net/phoenix/b7fa06ac993893703898b90bc2ca10c14128537.jpg',
              favCount: 66,
              poiId: '1690747119',
              dpPoiId: '1690747119'
            }
          ]
        },
        {
          city: '扬州',
          cityId: 321000,
          productList: [
            {
              productId: '6283769',
              price: 138,
              hostAvatarUrl: null,
              title: '【秋舍】之暖暖one，独立公寓超大落地窗，双人大床，小米电视，冰箱，洗衣机，免费饮料和小食，一次性马桶垫，洗衣液。',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '江阳路-开发路',
              starRating: 50,
              commentNumber: 31,
              coverImage: 'https://img.meituan.net/phoenix/4ebeb19c1ff5c0629bc6d98e822231c95460625.jpg',
              favCount: 324,
              poiId: '193121742',
              dpPoiId: '130160646'
            },
            {
              productId: '8632786',
              price: 168,
              hostAvatarUrl: null,
              title: '皮市街特色四合院民宿有天台院子落地窗大床房',
              rentType: 1,
              layoutRoom: 2,
              maxGuestNumber: 2,
              locationArea: '何园-1912街区',
              starRating: 46,
              commentNumber: 4,
              coverImage: 'https://img.meituan.net/iphoenix/d400ca004d5fef82da9f172ae9dcf2a42495277.jpg',
              favCount: 37,
              poiId: '1314174747',
              dpPoiId: '1314174747'
            },
            {
              productId: '6178417',
              price: 145,
              hostAvatarUrl: null,
              title: '明亮舒适·大床房·东关街/个园/古运河畔/瘦西湖附近，位置优越，可停车',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 3,
              locationArea: '梅岭',
              starRating: 49,
              commentNumber: 32,
              coverImage: 'http://p1.meituan.net/iphoenix/0203b4af64d27cb0da1f53f17fc5a32c3576576.jpg',
              favCount: 129,
              poiId: '192283335',
              dpPoiId: '129430973'
            },
            {
              productId: '2930341',
              price: 148,
              hostAvatarUrl: null,
              title: '扬州瘦西湖/万达笙箫风情投影客栈-1',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '万达广场',
              starRating: 50,
              commentNumber: 101,
              coverImage: 'https://img.meituan.net/phoenix/9bec08c16e8a91aad0565f93015e515f2968936.jpg',
              favCount: 597,
              poiId: '182453346',
              dpPoiId: '114897866'
            },
            {
              productId: '7282067',
              price: 148,
              hostAvatarUrl: null,
              title: '[尊品民宿]万达广场旁真皮大床独立吧区/瘦西湖/东关街/个园/何园直达密码自助',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '万达广场',
              starRating: 50,
              commentNumber: 38,
              coverImage: 'https://img.meituan.net/phoenix/9fe1d54b83ffb2268277289f36d8d787359472.jpg',
              favCount: 240,
              poiId: '194636795',
              dpPoiId: '131661719'
            },
            {
              productId: '2926855',
              price: 158,
              hostAvatarUrl: null,
              title: '古  月   家 Rainbow’s公馆.万达店。长租价更优',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '万达广场',
              starRating: 47,
              commentNumber: 41,
              coverImage: 'http://p0.meituan.net/phoenix/774e888cb0f2a7608bf0d9dfd31391fc1222132.jpg',
              favCount: 434,
              poiId: '182130010',
              dpPoiId: '114553162'
            }
          ]
        },
        {
          city: '嘉兴',
          cityId: 330400,
          productList: [
            {
              productId: '2767171',
              price: 148,
              hostAvatarUrl: null,
              title: '已消毒  万达广场正青春寓所  免费停车  情侣入住  南湖景区  高中园区',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '万达广场/动植物园',
              starRating: 49,
              commentNumber: 55,
              coverImage: 'https://img.meituan.net/phoenix/23b8db3c215f0644f56193fdb4815aa7855059.jpg',
              favCount: 315,
              poiId: '180075676',
              dpPoiId: '112628938'
            },
            {
              productId: '10470031',
              price: 115,
              hostAvatarUrl: null,
              title: '（已消毒）乌镇西栅景区for水木年华（部分临河）大床房/情侣出游/免费接送/免费停车/汉服租赁打折/可开发票/游玩攻略',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '乌镇',
              starRating: 50,
              commentNumber: 50,
              coverImage: 'https://img.meituan.net/phoenix/7566c634940ff75b7ef9b1bcfc8aefc4318860.jpg',
              favCount: 2115,
              poiId: '1587170814',
              dpPoiId: '1587170814'
            },
            {
              productId: '10643998',
              price: 228,
              hostAvatarUrl: null,
              title: '可做饭南都大厦嘉一医院，嘉兴学院附近八佰伴银泰百货万达广场一室一厅一卫',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 3,
              locationArea: '第一医院',
              starRating: 48,
              commentNumber: 11,
              coverImage: 'https://img.meituan.net/phoenix/91264a67fc3ce438fc92168607b20214724890.jpg',
              favCount: 75,
              poiId: '881272212',
              dpPoiId: '881272212'
            },
            {
              productId: '4470884',
              price: 128,
              hostAvatarUrl: null,
              title: '万达广场羽霓同行温馨小屋',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '万达广场/动植物园',
              starRating: 45,
              commentNumber: 4,
              coverImage: 'https://img.meituan.net/phoenix/8051af9afe422123927d43e5a808fac0700081.jpg',
              favCount: 88,
              poiId: '560016948',
              dpPoiId: '560016948'
            },
            {
              productId: '2715219',
              price: 178,
              hostAvatarUrl: null,
              title: '已消毒  万达广场森林风情寓所  情侣入住   同济大学嘉兴分院   高中园区',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '万达广场/动植物园',
              starRating: 49,
              commentNumber: 26,
              coverImage: 'http://p1.meituan.net/phoenix/93e2f50fb350df798bfa6b929602703b292322.jpg',
              favCount: 282,
              poiId: '179945333',
              dpPoiId: '112510956'
            },
            {
              productId: '9096245',
              price: 128,
              hostAvatarUrl: null,
              title: '「乔溪·半岛」乌镇近景区|西栅景区入口100米|交通方便|街景夜景',
              rentType: 0,
              layoutRoom: 1,
              maxGuestNumber: 2,
              locationArea: '乌镇',
              starRating: 50,
              commentNumber: 7,
              coverImage: 'https://img.meituan.net/iphoenix/9f98f5bc732b21918eb1ca2342863f4c574853.jpg',
              favCount: 197,
              poiId: '764718811',
              dpPoiId: '764718811'
            }
          ]
        }
      ],
      curCity: '上海',
      timer: null
    }
  },
  computed: {
    productList () {
      return (this.minsuList.filter(item => item.city === this.curCity)[0] || {}).productList || []
    }
  },
  methods: {
    onMouseEnter (e) {
      clearTimeout(this.timer)
      this.timer = setTimeout(() => {
        this.curCity = e.target.textContent.trim()
      }, 100)
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~assets/css/variables.scss';

.zhenguo-container {
  position: relative;
  margin: 40px auto;
  .index-nav-container {
    box-sizing: border-box;
    width: 100%;
    height: 44px;
    line-height: 44px;
    font-size: 14px;
    color: $color-white;
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
        border-bottom: 7px solid $color-white;
      }
    }
    .total {
      float: right;
      margin-right: 12px;
      a {
        color: $color-white;
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
  .minsu-ls-view {
    padding: 20px;
    padding-right: 0;
    padding-bottom: 0;
    background: $color-white;
    border: 1px solid $border-color-base;
    border-top: 0;
    border-bottom-left-radius: 4px;
    border-bottom-right-radius: 4px;
    .products {
      display: flex;
      flex-wrap: wrap;
    }
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
          border: 2px solid $color-white;
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
  }
}
</style>
