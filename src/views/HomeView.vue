<template>
  <div class="box" style="position: relative;left: 0;top: 0;">
      <Te @render="render" />
    <div class="sou">
      <Ho :num="num"/>
    </div>
  </div>
</template>
<script>
import Te from '../components/TeWorld.vue'
import Ho from '../components/YoWorld.vue'
export default {
  data() {
    return {
      num:0
    }
  },
  methods: {
    render(n){
      this.num=n
      // console.log(this.num,888);
    }
  },
  components:{
    Te,
    Ho,
  },
}
</script>
<style lang="less">
.xvc {
  content: "";
  border-radius: 3px;
  width: 3px;
  height: 14px;
  background-color: #1890ff;
  display: inline-block;
}

.u li:hover {
  background-color: #1890ff1a;
}

.bt {
  border-top: 1px solid #f2f2f2;
}

.asd {
  padding-bottom: .25rem;
  margin-top: .25rem;
}

.u li {
  margin: 2px 0;
  border-radius: 8px;
  color: rgba(var(--alpha-color), .7);
  line-height: 32px;
  height: 32px;
  font-size: 14px;
}

.u {
  width: 184px;
  height: 503px;
  padding-top: 4px;
}

.el-icon-search {
  line-height: 30px;
}

.sou {
  background-color: var(--bg-info);
  width: 800px;
  height: 600px;
}

.a {
  height: 30px;
  width: 162px;
}

.a input {
  width: 140px;
  height: 30px;
  border-radius: 6px;
  border: none;
  background: #F0F1F4;

}

.a {
  background: #F0F1F4;
  padding: 1px 11px;
  border-radius: 6px;
  display: flex;
}

.box {
  width: 1000px;
  height: 600px;
  display: flex;
  background: var(--bg-card);
  margin: auto;
  margin-top: 100px;
  display: flex;
}

.home {
  width: 184px;
  height: 570px;
  padding-top: 30px;
  padding-right: .5rem;
  padding-left: .5rem;
  background: #FFFFFF;
}
.box{
  background: #F5F5F5;
  box-shadow: 0 12px 32px #0000007a;
}
</style>