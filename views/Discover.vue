<template>
  <div>
    <!-- 导航栏开始 -->
    <mt-header class="sousuo" fixed>
      <div class="sousuo_div" slot="left"> 
        <router-link to="/search">
          <img src="../assets/index/sousuo.png" alt=""  class="sh_sousuo"> 
          <input type="text" name="" id="" placeholder="搜索动态"> 
        </router-link>
      </div>
      <div slot="right" class="sh_img">
        <router-link to="/">
          <img src="../assets/shopping/xiaoxi.png" alt="">
        </router-link>
      </div> 
    </mt-header>
    <!-- 导航栏结束 -->
    <div class="margin">
      <!-- 详情主页开始 -->
    <div class="discover" v-for="(i,k) of cont" :key="k">
      <div class="discover-info">
        <div class="discover-info-avatar">
          <img src="../assets/discover/touxiang.jpg" alt="">
        </div>
        <div class="discover-info-details">
          <div class="discover-info-nickname">BH85933907</div>
        </div>
        <div class="discover-info-follow">
         <span class="discover-info-follow-span"> 关注</span>
        </div>
      </div>
      <div class="discover-content">
        <div class="discover-content-text">
          #减肥日记##饮食日记# 9月打卡10/20，今天练肩（前束，中束，后束）+肱三。
          低碳日饮食：碳水摄入约60g，蛋白质约120g，脂肪约80g，热量约1500大卡。 
        ​​​</div>
        <div class="discover-item">
          <img class="discover-item-img" src="../assets/discover/zhaopian.jpg" alt="">
          <img class="discover-item-img" src="../assets/discover/zhaopian2.jpg" alt="">
          <img class="discover-item-img" src="../assets/discover/zhaopian3.jpg" alt="">
        </div>
        <div class="infoicon">
          <div class="infoicon-item"><img src="../assets/discover/dainzan.png" alt=""></div>
          <div class="infoicon-item"><img src="../assets/discover/pinglun.png" alt=""></div>
          <div class="infoicon-item"><img src="../assets/discover/shoucang.png" alt=""></div>
        </div> 
      </div>  
  </div>
    <!-- 详情主页结束 -->
    </div>
    
    <!--  -->
    <tabbar :selected="selected" fixed></tabbar>
  </div>
</template>
<style scoped>
.margin{
  margin-top: 83px;
}
/* 顶部导航栏开始 */
.sousuo{
  background-color:  #4fe0b5;
}
.sousuo_div>a>input{
  width: 200px;
  border-radius: 18px;
  border: 0;
  outline: 0;
  padding: 6px;
  padding-left: 20px;
  
}
.sousuo_div>a>img{
vertical-align: middle;
}
/* 顶部导航栏结束 */

/* .goog-te-spinner-pos{
  transition-delay: 0s;
} */

/* 详情主页开始 */
.discover{
  margin-top: 40px;
  background-color: #fff;
  border-bottom: 1px solid #ccc;
  box-shadow: 0 1px 3px rgba(26,26,26,0.1);
}
.discover:nth-child(1){
  margin-top: 40px;
}
.discover-info{
  display:flex;
  align-items: center;
  background-color: #fff;
  padding: 10px;
  margin-top: -40px;
}
/* 用户头像 */
.discover-info-avatar img{
  width: 40px;
  height: 40px;
  border-radius: 100%;
}
/* 用户昵称 */
.discover-info-details{
  font-size: 14px;
  margin-left: 5px;
}
/* 关注 */
.discover-info-follow{
  position: relative;
  width: 50px;
  height: 19px;
  color:#4fe0b5;
  line-height: 19px;
  border: 1px solid #4fe0b5;
  border-radius: 24px;
  margin-left: 167px;
}
.discover-info-follow-span{
  position: absolute;
  display: block;
  margin-left: 7px;
}
.discover-info-nickname{
  max-width: 100px;
  max-height: 13px;
  overflow: hidden;
}
/* 发表的内容和图片 */
.discover-content{
  position: relative;
  padding: 0 10px 10px 10px;
  background-color: #fff;
  line-height: 1.7;
}
/* 输入文本 */
discover-content-text{
  text-align: left;
  max-height: 140px;
  border-radius: 3px;
  overflow: hidden;
  letter-spacing: 1px;
}
/* 插入图片 */
.discover-item{
  margin: 10px 0;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.discover-item-img{
  display: flex;
  justify-content: center;
  width: 33%;
  border-radius: 7px;
}
/* 图标 */
.infoicon{
  width: 100%;
  display: flex;
  background-color:#fff;
}
.infoicon-item{
  width: 34%;
  height: 50px;
  line-height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.infoicon img{
  width: 25px;
  height: 25px;
}
/* 详情主页结束 */
</style>
<script>
import Tabbar from '../components/Tabbar.vue';
export default {
  components:{
        Tabbar
    },
  data(){
    return {
        cont:10,
        selected:'discover'
    }
  },
  watch:{
        //监听底部选项卡的变化
        selected (value) {
            switch(value){
                case 'index':
                    this.$router.push('/').catch(()=>{});
                    break;
                case 'discover':
                    this.$router.push('/discover').catch(()=>{});
                    break;
                case 'jia':
                    this.$router.push('/jia').catch(()=>{});
                    break;
                case 'shopping':
                    this.$router.push('/shopping').catch(()=>{});
                    break;
                case 'me':
                    this.$router.push('/me').catch(()=>{});
                    break;
            }
        }
    }
}
</script>