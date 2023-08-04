<template>
  <div class="home" style="position: relative;left: 0;top: 0;">
    <div>
      <h3 class="ta">微信读书</h3>
      <span class="el-icon-search"></span>
      <Sou/>
    </div>

    <div class="cen">
      <div class="z">
        <img src="https://www4.bing.com//th?id=OHR.ZelenciSprings_ZH-CN8022746409_1920x1080.jpg&rf=LaDigue_1920x1080.jpg&pid=hp&w=360&h=202" alt="" />
        &nbsp;&nbsp;&nbsp;<span style="color: white;font-size: 13px;">微信用户</span>&nbsp;&nbsp;&nbsp;
        <span style="opacity: 0.5;font-size: 13px;color: white;">体验卡今日到期</span>
      </div>
      <div style="display: flex;">
        <Wa/>
        <div style="float: right;margin-left: 63%;">
          <span style="line-height: 100px;color: white;">书架</span>
          <span class="el-icon-arrow-right" style="line-height: 100px;color: white;"></span>
        </div>
     </div>
    </div>
  <Tui />

  </div>
</template>
<style lang="less" scoped>
.cen {
  width: 90%;
  height: 200px;
  background: #575860;
  margin: auto;
  border-radius: 10px;
  margin-top: 20px;
  margin-bottom: 20px;
}
.z{
  padding: 20px;
  display: flex;
  align-items: center;
}
.cen .z img{
  width: 30px;
  height: 30px;
  border-radius: 20px;
}
.home {
  width: 100%;
  height: 100%;
}

.ta {
  text-align: center;
  margin-top: 20px;
}

.el-tabs__nav-scroll{
  position: sticky;
  top: 0;
}

.el-icon-search {
  position: absolute;
  left: 41px;
  top: 58px;
}
</style>
<script>
import Tui from '../components/TuiView.vue'
import Wa from '../components/WaView.vue'
import Sou from '../components/SouView.vue'
export default {
 data(){
  return{
    showSpinner: false
  }
 },
 methods:{
  checkScroll() {
      const contentElement = document.querySelector('.content');
      const scrollTop = contentElement.scrollTop;
      const scrollHeight = contentElement.scrollHeight;
      const clientHeight = contentElement.clientHeight;

      if (scrollTop + clientHeight >= scrollHeight) {
        this.showSpinner = true;
        setTimeout(() => {
          this.showSpinner = false;
        }, 2000);
      }
    }
 },
 components:{
  Tui,
  Wa,
  Sou
 }
}
</script>
<style lang="less" scoped>
.loading-spinner {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 50px;
  background-color: #f1f1f1;
  visibility: hidden;
  opacity: 0;
  transition: visibility 0s, opacity 0.5s;
}

.loading-spinner.active {
  visibility: visible;
  opacity: 1;
}

.spinner {
  width: 20px;
  height: 20px;
  border: 3px solid #ccc;
  border-top-color: #777;
  border-radius: 50%;
  animation: spinner-rotation 0.8s linear infinite;
}

@keyframes spinner-rotation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>