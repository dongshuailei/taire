<template>
    <div style="width: 1000px;height: 54px;">
      <el-tabs v-model="activeName" @tab-click="handleClick">
    <el-tab-pane label="我的订阅" name="first">
      <div style="display: flex;  flex-direction: row;">
        <!-- <Zuo  />
        <You /> -->
      </div>
    </el-tab-pane>
    <el-tab-pane label="全部" name="second">
      <div style="display: flex;flex-direction: row;">
        <Zuo :arr="da" @dada="funs()" @dataList="abc" />
        <You :you="da1"  :arrlist="arrlist"/>
      </div>
    </el-tab-pane>
    <el-tab-pane label="综合" name="third">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="zong"  @dada="funs()"  @dataList="abc"/>
        <You :you="zong1"  :arrlist="arrlist"/>
      </div>
    </el-tab-pane>
    <el-tab-pane label="科技" name="fourth">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="arr1"  @dada="funs()" @dataList="abc"/>
        <You  :you="arr2"  :arrlist="arrlist"/>
      </div>
    </el-tab-pane>
    <el-tab-pane label="娱乐" name="one">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="yu"  @dada="funs()" @dataList="abc"/>
        <You :you="yu1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="社区" name="two">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="sheji"  @dada="funs()" @dataList="abc"/>
        <You :you="sheji1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="购物" name="theer">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="gou"  @dada="funs()" @dataList="abc"/>
        <You :you="gou1"  :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="财经" name="fore">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="cai"  @dada="funs()" @dataList="abc"/>
        <You :you="cai1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="大学" name="fv">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="xue"  @dada="funs()" @dataList="abc"/>
        <You :you="xue1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="日报" name="se">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="ri"  @dada="funs()" @dataList="abc"/>
        <You :you="ri1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="地方门户" name="sa">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="gao"  @dada="funs()" @dataList="abc"/>
        <You :you="gao1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="影视" name="at">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="ying"  @dada="funs()" @dataList="abc"/>
        <You :you="ying1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="阅读" name="el">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="yue"  @dada="funs()" @dataList="abc"/>
        <You :you="yue1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="游戏" name="mu">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="you"  @dada="funs()" @dataList="abc"/>
        <You :you="you1"  :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="体育" name="q">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="ti" @dada="funs()" @dataList="abc"/>
        <You :you="ti1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="产品" name="w">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="chan" @dada="funs()" @dataList="abc"/>
        <You :you="chan1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="开发" name="e">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="kai" @dada="funs()" @dataList="abc"/>
        <You :you="kai1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="设计" name="t">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="she" @dada="funs()" @dataList="abc"/>
        <You :you="she1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="应用" name="r">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="yingyong" @dada="funs()" @dataList="abc"/>
        <You :you="yingyong1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="汽车" name="y">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="qi" @dada="funs()" @dataList="abc"/>
        <You :you="qi1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
    <el-tab-pane label="安全" name="u">
      <div style="display: flex;    flex-direction: row;">
        <Zuo :arr="an" @dada="funs()" @dataList="abc"/>
        <You :you="an1" :arrlist="arrlist" />
      </div>
    </el-tab-pane>
  </el-tabs>
    </div>
  </template>
  <script>
  import Zuo from './ZuoView.vue'
  import You from './YouView.vue'
  // import yingshi from './YiShi.vue'
  import Da from '../components/da.json'
  // import DaYing from '../components/../components/DaYing.vue'
  export default {
    data() {
      return {
        activeName: 'second',
        us:[],
        arr1:[
        {
            "name": "36氧",
            "img": "https://files.codelife.cc/topsearch/Q1Vd5Ko85R.png"
          },
          {
            "name": "少数派",
            "img": "https://files.codelife.cc/topsearch/Y2KeDGQdNP.png"
          },
          {
            "name": "虎嗅网",
            "img": "https://files.codelife.cc/topsearch/5VaobgvAj1.png"
          },
          {
            "name": "IT之家",
            "img": "https://files.codelife.cc/topsearch/74Kvx59dkx.png"
          },
        ],
        arr2:[
        {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏12312312看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
        ],
        da:[
        {
          "img": "https://files.codelife.cc/topsearch/KqndgxeLl9.png",
          "name": "微博"
        },
        {
          "name": "知乎",
          "img": "https://files.codelife.cc/topsearch/mproPpoq6O.png"
        },
        {
            "name": "微信",
            "img": "https://files.codelife.cc/topsearch/WnBe01o371.png"
          },
          {
            "name": "百度",
            "img": "https://files.codelife.cc/topsearch/Jb0vmloB1G.png"
          },
          {
            "name": "36氧",
            "img": "https://files.codelife.cc/topsearch/Q1Vd5Ko85R.png"
          },
          {
            "name": "少数派",
            "img": "https://files.codelife.cc/topsearch/Y2KeDGQdNP.png"
          },
          {
            "name": "虎嗅网",
            "img": "https://files.codelife.cc/topsearch/5VaobgvAj1.png"
          },
          {
            "name": "IT之家",
            "img": "https://files.codelife.cc/topsearch/74Kvx59dkx.png"
          },
          {
            "name": "哔哩哔哩",
            "img": "https://files.codelife.cc/topsearch/74KvxwokxM.png"
          },
          {
            "name": "抖音",
            "img": "https://files.codelife.cc/topsearch/DpQvNABoNE.png"
          },
          {
            "name": "煎蛋",
            "img": "https://files.codelife.cc/topsearch/NRrvWq3e5z.png"
          },
          {
            "name": "AcFun",
            "img": "https://files.codelife.cc/topsearch/qENeYpdY49.png"
          },
          {
            "name": "吾爱破解",
            "img": "https://files.codelife.cc/topsearch/NKGoRAzel6.png"
          },
          {
            "name": "百度贴吧",
            "img": "https://files.codelife.cc/topsearch/Om4ejxvxEN.png"
          },
          {
            "name": "腾讯新闻",
            "img": "https://files.codelife.cc/topsearch/12owgX0oNV.png"
          },
          {
            "name": "虎扑社区",
            "img": "https://files.codelife.cc/topsearch/G47o8weMmN.png"
          },
          {
            "name": "淘宝·天猫",
            "img": "https://files.codelife.cc/topsearch/yjvQDpjobg.png"
          },{
            "name": "什么值得购买",
            "img": "https://files.codelife.cc/topsearch/K7GdagpoQy.png"
          },
          {
            "name": "今日热卖",
            "img": "https://files.codelife.cc/topsearch/x9ozqX7eXb.png"
          },
          {
            "name": "淘宝",
            "img": "https://files.codelife.cc/topsearch/0MdKLK2ew1.png"
          },
          {
            "name": "雪球",
            "img": "https://files.codelife.cc/topsearch/X12owXzvNV.png"
          },
          {
            "name": "第一财经",
            "img": "https://files.codelife.cc/topsearch/0MdKam4ow1.png"
          },
          {
            "name": "财新网",
            "img": "https://files.codelife.cc/topsearch/x9ozBY7oXb.png"
          },
          {
            "name": "新浪财经新闻",
            "img": "https://files.codelife.cc/topsearch/rx9ozj7oXb.png"
          },
          {
            "name": "水木社区",
            "img": "https://files.codelife.cc/topsearch/rDgeyqeZqJ.png"
          },
          {
            "name": "北大末名",
            "img": "https://files.codelife.cc/topsearch/MZd7zXPvrO.png"
          },
          {
            "name": "北邮人论坛",
            "img": "https://files.codelife.cc/topsearch/Q0orpqOd8B.png"
          },{
            "name": "知乎日报",
            "img": "https://files.codelife.cc/topsearch/KMZd7VOvrO.png"
          },
          {
            "name": "开眼视频",
            "img": "https://files.codelife.cc/topsearch/KqndgDmeLl.png"
          }
        ],
        da1:[
        {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
        ],
        zong:[
        {
        "img": "https://files.codelife.cc/topsearch/KqndgxeLl9.png",
        "name": "微博"
      },
      {
        "name": "知乎",
        "img": "https://files.codelife.cc/topsearch/mproPpoq6O.png"
      },
      {
          "name": "微信",
          "img": "https://files.codelife.cc/topsearch/WnBe01o371.png"
        },
        {
          "name": "百度",
          "img": "https://files.codelife.cc/topsearch/Jb0vmloB1G.png"
        },
        {
          "name": "今日头条",
          "img": "https://files.codelife.cc/icons/toutiao.svg"
        }
        ],
        zong1:[
        {
        "img": "1",
        "name": "成毅跳queencard 认真中带着幽默",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "央视网文娱评长月烬明",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "再紧急预拨14.6亿元支持京津冀黑吉救灾",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "再紧急预拨14.6亿元支持京津冀黑吉救灾",
        "i":"98.8万"
      }
        ],
        yu:[
        {
            "name": "哔哩哔哩",
            "img": "https://files.codelife.cc/topsearch/74KvxwokxM.png"
          },
          {
            "name": "抖音",
            "img": "https://files.codelife.cc/topsearch/DpQvNABoNE.png"
          },
          {
            "name": "煎蛋",
            "img": "https://files.codelife.cc/topsearch/NRrvWq3e5z.png"
          },
          {
            "name": "AcFun",
            "img": "https://files.codelife.cc/topsearch/qENeYpdY49.png"
          },
          {
            "name": "中文播客榜",
            "img": "https://files.codelife.cc/topsearch/NKGoRAzel6.png"
          },
        ],
        yu1:[
        {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
        ],
       she:[
       {
            "name": "吾爱破解",
            "img": "https://files.codelife.cc/topsearch/NKGoRAzel6.png"
          },
          {
            "name": "百度贴吧",
            "img": "https://files.codelife.cc/topsearch/Om4ejxvxEN.png"
          },
          {
            "name": "腾讯新闻",
            "img": "https://files.codelife.cc/topsearch/12owgX0oNV.png"
          },
          {
            "name": "虎扑社区",
            "img": "https://files.codelife.cc/topsearch/G47o8weMmN.png"
          },
       ],
       she1:[
       {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
       ],
       gou:[
       {
            "name": "淘宝·天猫",
            "img": "https://files.codelife.cc/topsearch/yjvQDpjobg.png"
          },{
            "name": "什么值得购买",
            "img": "https://files.codelife.cc/topsearch/K7GdagpoQy.png"
          },
          {
            "name": "今日热卖",
            "img": "https://files.codelife.cc/topsearch/x9ozqX7eXb.png"
          },
          {
            "name": "淘宝",
            "img": "https://files.codelife.cc/topsearch/0MdKLK2ew1.png"
          },
       ],
       gou1:[
       {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
       ],
       cai:[
       {
            "name": "雪球",
            "img": "https://files.codelife.cc/topsearch/X12owXzvNV.png"
          },
          {
            "name": "第一财经",
            "img": "https://files.codelife.cc/topsearch/0MdKam4ow1.png"
          },
          {
            "name": "财新网",
            "img": "https://files.codelife.cc/topsearch/x9ozBY7oXb.png"
          },
          {
            "name": "新浪财经新闻",
            "img": "https://files.codelife.cc/topsearch/rx9ozj7oXb.png"
          },
       ],
       cai1:[
       {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
       ],
       xue:[
       {
            "name": "水木社区",
            "img": "https://files.codelife.cc/topsearch/rDgeyqeZqJ.png"
          },
          {
            "name": "北大末名",
            "img": "https://files.codelife.cc/topsearch/MZd7zXPvrO.png"
          },
          {
            "name": "北邮人论坛",
            "img": "https://files.codelife.cc/topsearch/Q0orpqOd8B.png"
          },
       ],
       xue1:[
       {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
       ],
       ri:[{
            "name": "知乎日报",
            "img": "https://files.codelife.cc/topsearch/KMZd7VOvrO.png"
          },
          {
            "name": "开眼视频",
            "img": "https://files.codelife.cc/topsearch/KqndgDmeLl.png"
          },
          {
            "name":"历史上的今天",
            "img:":"https://files.codelife.cc/topsearch/KMZd7X3erO.png"
          },
          {
            "name": "哔哩哔哩",
            "img": "https://files.codelife.cc/topsearch/74KvxwokxM.png"
          },
        ],
       ri1:[   {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }],

      gao:[
      {
            "name": "高楼迷",
            "img": "https://files.codelife.cc/topsearch/YqoXQEqvOD.png"
          },
          {
            "name": "宽带山",
            "img": "https://files.codelife.cc/topsearch/Jb0vml8oB1.png"
          },{
            "name": "厦门小鱼",
            "img": "https://files.codelife.cc/topsearch/rYqoXz6dOD.png"
          },
          {
            "name": "过早课",
            "img": "https://files.codelife.cc/topsearch/KMZd76vrOw.png"
          }
      ],
      gao1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      ying:[
      {
            "name": "煎蛋",
            "img": "https://files.codelife.cc/topsearch/NRrvWq3e5z.png"
          },
          {
            "name": "AcFun",
            "img": "https://files.codelife.cc/topsearch/qENeYpdY49.png"
          },
          {
            "name": "吾爱破解",
            "img": "https://files.codelife.cc/topsearch/NKGoRAzel6.png"
          },
          {
            "name": "百度贴吧",
            "img": "https://files.codelife.cc/topsearch/Om4ejxvxEN.png"
          },
          {
            "name": "腾讯新闻",
            "img": "https://files.codelife.cc/topsearch/12owgX0oNV.png"
          },
      ],
      ying1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      yue:[
      {
            "name": "虎扑社区",
            "img": "https://files.codelife.cc/topsearch/G47o8weMmN.png"
          },
          {
            "name": "淘宝·天猫",
            "img": "https://files.codelife.cc/topsearch/yjvQDpjobg.png"
          },{
            "name": "什么值得购买",
            "img": "https://files.codelife.cc/topsearch/K7GdagpoQy.png"
          },
          {
            "name": "今日热卖",
            "img": "https://files.codelife.cc/topsearch/x9ozqX7eXb.png"
          },
      ],
      yue1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      you:[
      {
            "name": "第一财经",
            "img": "https://files.codelife.cc/topsearch/0MdKam4ow1.png"
          },
          {
            "name": "财新网",
            "img": "https://files.codelife.cc/topsearch/x9ozBY7oXb.png"
          },
          {
            "name": "新浪财经新闻",
            "img": "https://files.codelife.cc/topsearch/rx9ozj7oXb.png"
          },
          {
            "name": "水木社区",
            "img": "https://files.codelife.cc/topsearch/rDgeyqeZqJ.png"
          },
      ],
      you1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      ti:[
          {"name": "北大末名",
            "img": "https://files.codelife.cc/topsearch/MZd7zXPvrO.png"
          },
          {
            "name": "北邮人论坛",
            "img": "https://files.codelife.cc/topsearch/Q0orpqOd8B.png"
          },{
            "name": "知乎日报",
            "img": "https://files.codelife.cc/topsearch/KMZd7VOvrO.png"
          },
          {
            "name": "开眼视频",
            "img": "https://files.codelife.cc/topsearch/KqndgDmeLl.png"
          },
          {
            "name": "高楼迷",
            "img": "https://files.codelife.cc/topsearch/YqoXQEqvOD.png"
          },
      ],
      ti1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      chan:[
      {
            "name": "吾爱破解",
            "img": "https://files.codelife.cc/topsearch/NKGoRAzel6.png"
          },
          {
            "name": "百度贴吧",
            "img": "https://files.codelife.cc/topsearch/Om4ejxvxEN.png"
          },
          {
            "name": "腾讯新闻",
            "img": "https://files.codelife.cc/topsearch/12owgX0oNV.png"
          },
          {
            "name": "虎扑社区",
            "img": "https://files.codelife.cc/topsearch/G47o8weMmN.png"
          },
      ],
      chan1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      kai:[
      {
            "name": "雪球",
            "img": "https://files.codelife.cc/topsearch/X12owXzvNV.png"
          },
          {
            "name": "第一财经",
            "img": "https://files.codelife.cc/topsearch/0MdKam4ow1.png"
          },
          {
            "name": "财新网",
            "img": "https://files.codelife.cc/topsearch/x9ozBY7oXb.png"
          },
          {
            "name": "新浪财经新闻",
            "img": "https://files.codelife.cc/topsearch/rx9ozj7oXb.png"
          },
      ],
      kai1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      sheji:[
      {
            "name": "水木社区",
            "img": "https://files.codelife.cc/topsearch/rDgeyqeZqJ.png"
          },
          {
            "name": "北大末名",
            "img": "https://files.codelife.cc/topsearch/MZd7zXPvrO.png"
          },
          {
            "name": "北邮人论坛",
            "img": "https://files.codelife.cc/topsearch/Q0orpqOd8B.png"
          },{
            "name": "知乎日报",
            "img": "https://files.codelife.cc/topsearch/KMZd7VOvrO.png"
          },
          {
            "name": "开眼视频",
            "img": "https://files.codelife.cc/topsearch/KqndgDmeLl.png"
          },
      ],
      sheji1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      yingyong:[
      {
            "name": "淘宝·天猫",
            "img": "https://files.codelife.cc/topsearch/yjvQDpjobg.png"
          },{
            "name": "什么值得购买",
            "img": "https://files.codelife.cc/topsearch/K7GdagpoQy.png"
          },
          {
            "name": "今日热卖",
            "img": "https://files.codelife.cc/topsearch/x9ozqX7eXb.png"
          },
          {
            "name": "淘宝",
            "img": "https://files.codelife.cc/topsearch/0MdKLK2ew1.png"
          },
      ],
      yingyong1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      qi:[
      {
            "name": "雪球",
            "img": "https://files.codelife.cc/topsearch/X12owXzvNV.png"
          },
          {
            "name": "第一财经",
            "img": "https://files.codelife.cc/topsearch/0MdKam4ow1.png"
          },
          {
            "name": "财新网",
            "img": "https://files.codelife.cc/topsearch/x9ozBY7oXb.png"
          },
          {
            "name": "新浪财经新闻",
            "img": "https://files.codelife.cc/topsearch/rx9ozj7oXb.png"
          },
          {
            "name": "水木社区",
            "img": "https://files.codelife.cc/topsearch/rDgeyqeZqJ.png"
          },
      ],
      qi1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }
      ],
      an:[
      {
            "name": "北大末名",
            "img": "https://files.codelife.cc/topsearch/MZd7zXPvrO.png"
          },
          {
            "name": "北邮人论坛",
            "img": "https://files.codelife.cc/topsearch/Q0orpqOd8B.png"
          },{
            "name": "知乎日报",
            "img": "https://files.codelife.cc/topsearch/KMZd7VOvrO.png"
          },
          {
            "name": "开眼视频",
            "img": "https://files.codelife.cc/topsearch/KqndgDmeLl.png"
          },
          {
            "name": "高楼迷",
            "img": "https://files.codelife.cc/topsearch/YqoXQEqvOD.png"
          },
          {
            "name": "宽带山",
            "img": "https://files.codelife.cc/topsearch/Jb0vml8oB1.png"
          },{
            "name": "厦门小鱼",
            "img": "https://files.codelife.cc/topsearch/rYqoXz6dOD.png"
          },
      ],
      an1:[
      {
        "img": "1",
        "name": "高叶狂飙后首部电视剧",
        "i":"150.1万"
      },
      {
        "img": "2",
        "name": "王鹤棣终于演了西装暴徒",
        "i":"109.7万"
      },
      {
        "img": "3",
        "name": "大戏看北京",
        "i":"102.8万"
      },
      {
        "img": "4",
        "name": "大爷高铁上戴耳机喝白酒全程安静",
        "i":"98.8万"
      }  ],
      arrlist:{
        name:'微博',
        img:'https://files.codelife.cc/topsearch/KqndgxeLl9.png',
        index:0,
      }
      };
      
    },
    methods: {
      abc(data){
        this.arrlist=data
      },
      funs(){
        this.dds=sessionStorage.getItem('arr')
      },
      handleClick(tab) {
        sessionStorage.setItem('listzhi',tab.index)
      }
    },
    components:{
      Zuo,
      You,
    },
    mounted(){
       this.us = Da[0].category
    }
  };
  </script>
  <style lang="less" scoped>
  
  </style>