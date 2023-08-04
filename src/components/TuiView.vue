<template>
    <el-tabs v-model="activeName" @tab-click="handleClick" class="asd">
      <el-tab-pane label="推荐" name="first">
          <div v-for="(item,index) in list" :key="index" style="display: flex;flex-wrap: wrap;margin-top: 20px;">
             <img :src="item.url" alt="" style="width: 60px;height: 100px;">
             <div style="margin-left: 20px;width: 79%;">
             <p style="width: 100%;height: 20px;font-size: 18px;margin-top: 10px;">{{ item.title }}</p>
             <span style="width: 55%;height: 20px;font-size: 15px;opacity: 0.4;margin-top: 10px;display: inline-block;">{{ item.ob }}</span>&nbsp;&nbsp;
             <span style="width: 27%;height: 20px;color: red;margin-top: 10px;display: inline-block;font-size: 12px;opacity: 0.4;" :style="{ color: item.hao === '好评如潮' ? 'red' : '#C2962C' }">{{ item.hao }}</span><br>
             <span style="width: 100%;height: 20px;font-size: 14px;opacity: 0.4;display: inline-block;">{{ item.da }}</span>
             </div>
          </div>

      </el-tab-pane>
      <el-tab-pane label="分类" name="second">
        <div v-for="(item,index) in arr" :key="index" style="background: #F8F8FA;width: 90%;border-radius: 10px;display: flex;margin-top: 20px;height: 150px;align-items: center;">
             <div style="margin-left: 20px;width: 79%;display: flex;flex-direction: column;">
             <p style="font-size: 20px;margin-top: 10px;">{{ item.a }}</p>
             <span style="margin-top: 10px;opacity: 0.4;">{{ item.title }}</span>
             <span style="margin-top: 10px;opacity: 0.4;">{{ item.ob }}</span>
             <span style="margin-top: 10px;opacity: 0.4;">{{ item.da }}</span>
             </div>
             <img :src="item.url" alt="" style="width: 60px;height: 100px;">
        </div>

      </el-tab-pane>
      <el-tab-pane label="排行" name="third">
        <div v-for="(item,index) in list1" :key="index" style="display: flex;align-items: center;margin-top: 20px;">
            <span>{{ item.shu }}</span>
            <img :src="item.url" alt="" style="width: 60px;height: 100px;margin-left: 10px;">
            <div style="display: flex;flex-direction: column;margin-left: 20px;">
              <span>{{ item.title }}
              <span style="float: right;margin-right: 20px;font-size: 12px;opacity: 0.4;">{{ item.ren }}</span>
              </span>
              <span style="opacity: 0.4;margin-top: 5px;">{{ item. ob}}</span>
              <span style="width: 290px;opacity: 0.4;margin-top: 5px;">{{ item.da }}
              <span style="color: red;margin-top: 8px;" :style="{ color: item.hao === '好评如潮' ? 'red' : '#C2962C' }">{{ item.hao }}</span>
              </span>

            </div>
        </div>
      </el-tab-pane>
      <el-tab-pane label="文学艺术" name="fourth">
        <div v-for="(item,index) in list2" :key="index" style="display: flex;align-items: center;margin-top: 20px;">
            <span>{{ item.shu }}</span>
            <img :src="item.url" alt="" style="width: 60px;height: 100px;margin-left: 10px;">
            <div style="display: flex;flex-direction: column;margin-left: 20px;">
              <span>{{ item.title }}
              <span style="float: right;margin-right: 20px;font-size: 12px;opacity: 0.4;">{{ item.ren }}</span>
              </span>
              <span style="opacity: 0.4;margin-top: 5px;">{{ item. ob}}</span>
              <span style="width: 290px;opacity: 0.4;margin-top: 5px;">{{ item.da }}
              <span style="color: red;margin-top: 8px;" :style="{ color: item.hao === '好评如潮' ? 'red' : '#C2962C' }">{{ item.hao }}</span>
              </span>

            </div>
        </div>
      </el-tab-pane>
      <el-tab-pane label="哲学社科" name="one"> 
        <div v-for="(item,index) in list3" :key="index" style="display: flex;align-items: center;margin-top: 20px;">
            <span>{{ item.shu }}</span>
            <img :src="item.url" alt="" style="width: 60px;height: 100px;margin-left: 10px;">
            <div style="display: flex;flex-direction: column;margin-left: 20px;">
              <span>{{ item.title }}
              <span style="float: right;margin-right: 20px;font-size: 12px;opacity: 0.4;">{{ item.ren }}</span>
              </span>
              <span style="opacity: 0.4;margin-top: 5px;">{{ item. ob}}</span>
              <span style="width: 290px;opacity: 0.4;margin-top: 5px;">{{ item.da }}
              <span style="color: red;margin-top: 8px;" :style="{ color: item.hao === '好评如潮' ? 'red' : '#C2962C' }">{{ item.hao }}</span>
              </span>
            </div>
        </div>
      </el-tab-pane>
    </el-tabs>

  </template>
  <script>
    export default {
      data() {
        return {
          list:[
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/17/yuewen_23484983/t6_yuewen_234849831690286968.jpg',
              title:'长相思   (杨紫 张晚意 邓为)',
              ob:'桐华 | 推荐值89.5%',
              hao:'好评如潮',
              da:'大家都在读'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/75/cpPlatform_dbb14284a55f1e733b60202b0777255d/t6_cpPlatform_dbb14284a55f1e733b60202b0777255d.jpg',
              title:'长安的荔枝',
              ob:'马伯庸 | 推荐值95.5%',
              hao:'神作',
              da:'大家都在读'
            },
            {
              url:'https://wfqqreader-1252317822.image.myqcloud.com/cover/334/933334/t6_933334.jpg',
              title:'龙族（1-4合集）',
              ob:'江南 | 推荐值90.0%',
              hao:'神作',
              da:'大家都在读'
            },
            {
              url:'https://wfqqreader-1252317822.image.myqcloud.com/cover/385/25615385/t6_25615385.jpg',
              title:'被讨厌的勇气："自我启发之父"',
              ob:'岸见一郎 | 推荐值87.0%',
              hao:'好评如潮',
              da:'大家都在读'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/86/YueWen_33628204/t6_YueWen_33628204.jpg',
              title:'认知觉醒：开启自我改变的原动力',
              ob:'周岭 | 推荐值91.3%',
              hao:'神作',
              da:'大家都在读'
            },
          ],
          arr:[
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/17/yuewen_23484983/t6_yuewen_234849831690286968.jpg',
              a:'精品小说',
              title:'1.长相思   (杨紫 张晚意 邓为)',
              ob:'2.剑来',
              da:'3.三体（全集）'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/61/YueWen_822995/t6_YueWen_822995.jpg',
              a:'历史',
              title:'1.明朝那些事（全集）',
              ob:'2.长安的荔枝',
              da:'3.殷周之变'
            },
            {
              url:'https://wfqqreader-1252317822.image.myqcloud.com/cover/44/674044/t6_674044.jpg',
              a:'文学',
              title:'1.我与地坛',
              ob:'2.红楼梦',
              da:'3.平凡的世界（全三册）'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/84/YueWen_33514727/t6_YueWen_33514727.jpg',
              a:'艺术',
              title:'1.生活蒙太奇',
              ob:'2.故事：材质',
              da:'3.新摄影笔记'
            },
            {
              url:'https://wfqqreader-1252317822.image.myqcloud.com/cover/48/674048/t6_674048.jpg',
              a:'人物传记',
              title:'1.邓小平时代',
              ob:'2.毛泽东传（全6卷）',
              da:'3.苏东坡传（纪念典藏版）'
            },
          ],
          list1:[
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/94/cpplatform_akrjnymgoxljkqszganvbx/t6_cpplatform_akrjnymgoxljkqszganvbx1682248200.jpg',
              shu:'1',
              title:'厌女（增订版）',
              ob:'上野千鹤子',
              da:'推荐值89.1%',
              hao:'好评如潮',
              ren:'3761'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/40/3300012940/t6_3300012940.jpg',
              shu:'2',
              title:'法治的细节',
              ob:'罗翔',
              da:'推荐值93.9%',
              hao:'神作',
              ren:'3425'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/43/cpplatform_uksuobynut7k8guvdp7jpb/t6_cpplatform_uksuobynut7k8guvdp7jpb1690794764.jpg',
              shu:'3',
              title:'快乐上等',
              ob:'上野千鹤子 汤山玲子',
              da:'推荐值78.9%',
              ren:'2422'
            },
            {
              url:'https://wfqqreader-1252317822.image.myqcloud.com/cover/686/237686/t6_237686.jpg',
              shu:'4',
              title:'乡上中国',
              ob:'费孝通',
              da:'推荐值85.5%',
              hao:'好评如潮',
              ren:'2114'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/11/cpPlatform_fLkPGcXyQDk1Dogx6F3uxA/t6_cpPlatform_fLkPGcXyQDk1Dogx6F3uxA.jpg',
              shu:'5',
              title:'始于极限',
              ob:'上野千鹤子 铃木凉美',
              da:'推荐值90.6%',
              hao:'神作',
              ren:'1898'
            },
          ],
          list2:[
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/99/YueWen_42766048/t6_YueWen_42766048.jpg',
              shu:'1',
              title:'枪炮·病菌与钢铁',
              ob:'贾雷德',
              da:'推荐值87.3%',
              hao:'好评如潮',
              ren:'1438'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/89/cpPlatform_nVqL1T1SuysradaMks3Dbi/t6_cpPlatform_nVqL1T1SuysradaMks3Dbi.jpg',
              shu:'2',
              title:'小镇喧嚣',
              ob:'吴毅',
              da:'推荐值96.2%',
              hao:'神作',
              ren:'1168'
            },
            {
              url:'https://wfqqreader-1252317822.image.myqcloud.com/cover/732/40457732/t6_40457732.jpg',
              shu:'3',
              title:'圆圈正义',
              ob:'罗翔',
              da:'推荐值96.2%',
              ren:'1123',
              hao:'神作'
            },
            {
              url:'https://wfqqreader-1252317822.image.myqcloud.com/cover/295/32746295/t6_32746295.jpg',
              shu:'4',
              title:'刑法学讲义',
              ob:'罗翔',
              da:'推荐值93.4%',
              hao:'神作',
              ren:'901'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/10/cpplatform_3300004399/t6_cpplatform_33000043991677502000.jpg',
              shu:'5',
              title:'从零开始的女性主义',
              ob:'上野千鹤子 田房永子',
              da:'推荐值90.7%',
              hao:'神作',
              ren:'894'
            },
          ],
          list3:[
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/52/YueWen_40055543/t6_YueWen_40055543.jpg',
              shu:'1',
              title:'置身事内',
              ob:'兰小欢',
              da:'推荐值96.4%',
              hao:'神作',
              ren:'7887'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/89/YueWen_44026191/t6_YueWen_44026191.jpg',
              shu:'2',
              title:'纳瓦尔宝典',
              ob:'欸克里·桥根森',
              da:'推荐值88.3%',
              hao:'好评如潮',
              ren:'5501'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/68/YueWen_23601930/t6_YueWen_23601930.jpg',
              shu:'3',
              title:'富爸爸穷爸爸',
              ob:'罗伯特',
              da:'推荐值85.1%',
              ren:'3835',
              hao:'好评如潮'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/82/cpplatform_7fknrczhjmrhcrf8vygbvx/t6_cpplatform_7fknrczhjmrhcrf8vygbvx1686134532.jpg',
              shu:'4',
              title:'芯片战争',
              ob:'克里斯',
              da:'推荐值87.8%',
              hao:'好评如潮',
              ren:'2492'
            },
            {
              url:'https://weread-1258476243.file.myqcloud.com/weread/cover/25/cpplatform_8numzl8erzinxvfsk3p9jv/t6_cpplatform_8numzl8erzinxvfsk3p9jv1685508354.jpg',
              shu:'5',
              title:'资本的秘密',
              ob:'赫尔南多',
              da:'推荐值83.6%',
              ren:'2216'
            },
          ],
          activeName: 'first'
        };
      },
      methods: {
        handleClick(tab, event) {
          console.log(tab, event);
        },
      },
    };
  </script>
  <style lang="less" scoped>
  .asd{
    margin-left: 20px;
  }
  </style>