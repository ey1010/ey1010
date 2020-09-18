<template >
  <div>
    <!-- 顶部导航开始 -->
   <mt-header class="header" fixed>
       <div slot="right" id="header_img">
          <img src="../assets/index/qiandao.png" alt="" @click="show_qiandao" v-if="!this.$store.state.qiandao" >
          <p v-else>已签到{{this.$store.state.qdnum}}天</p>
       </div>
       <div class="header_input" slot="left">
         <router-link to="/search">
           <img src="../assets/index/sousuo.png" alt=""  class="header_input_img"> 
           <input type="text" name="" id="" placeholder="搜索食物">
         </router-link>
     </div> 
   </mt-header>
    <!-- 顶部导航结束 -->
    <!-- 面板开始 -->
    
    <!-- 轮播图开始 -->
    <div>
      <mt-swipe :auto=4000 :showIndicators="true" class=" mint-swipe">
        <mt-swipe-item class="mint-swipe-item">
          <img src="../assets/index/1.png" alt="" class="swipe_img1">
        </mt-swipe-item>
        <mt-swipe-item class="mint-swipe-item">
          <img src="../assets/index/2.png" alt="" class="swipe_img1">
        </mt-swipe-item>
        <mt-swipe-item class="mint-swipe-item">
          <img src="../assets/index/3.png" alt="" class="swipe_img1">
        </mt-swipe-item>
        <mt-swipe-item class="mint-swipe-item">
          <img src="../assets/index/4.png" alt="" class="swipe_img1">
        </mt-swipe-item>
      </mt-swipe>
    </div>
    <!-- 轮播图结束 -->
    <!-- 签到框显示开始 -->
    <mt-popup  v-model="popupVisible"  popup-transition="popup-fade" modal=true; class="mtpopup">
      <h1>签到提示</h1>
      <button @click="queding" class="mtpopup_button">签到成功</button>
    </mt-popup>
    <!-- 签到框显示结束 -->
    <!-- 状态栏开始 -->
    <div class="mianban">
      <mt-navbar v-model="active_1" class="daohang">
            <mt-tab-item id="1" class="dh">体重记录</mt-tab-item>
            <mt-tab-item id="2">饮食记录</mt-tab-item>
            <mt-tab-item id="3">制定食物</mt-tab-item>
      </mt-navbar>
      <mt-tab-container v-model="active_1">
        <mt-tab-container-item id="1">
          <div class="cont">
            <div>
              <img src="../assets/index/qicai.png" alt="">
              <i>已经减肥(天数)</i>
              <span>6</span>
            </div>
            <div>
              <img src="../assets/index/cheng.png" alt="">
              <i>当前体重(公斤)</i>
              <span>53.3</span>
            </div>
            <div>
              <img src="../assets/index/yao.png" alt="">
              <i>目标体重(公斤)</i>
              <span>50.0</span>
            </div>
          </div>
        </mt-tab-container-item>
        <mt-tab-container-item id="2">
          <div class="cont2">
            <div>
              <i>早餐</i>
              <span>建议359-439千卡</span>
              <img src="../assets/index/jiacan.png" alt="">
            </div>
            <div>
              <i>午餐</i>
              <span>建议479-585千卡</span>
              <img src="../assets/index/jiacan.png" alt="">
            </div>
            <div>
              <i>晚餐</i>
              <span>建议359-439千卡</span>
              <img src="../assets/index/jiacan.png" alt="">
            </div>
          </div>
        </mt-tab-container-item>
        <mt-tab-container-item id="3">
          <div class="cont3">
            <img src="../assets/index/shiwu.png" alt="">
            <p>根据你的个人喜好</p>
            <p>为你制定符合自己的健康营养餐</p>
          </div>
          <button class="btn">查看详情</button>
        </mt-tab-container-item>
      </mt-tab-container>
    </div>
    <!-- 状态栏结束 -->
    <!-- 推荐栏开始 -->
    <div class="Dapush">
      <div class="Dapush_Da">
        <div class="Dapush_div"></div>
        <p>今日推荐</p><hr>
      </div>
      <div class="Dapush_img">
        <div>
          <img src="../assets/index/tuijian1.png" alt="" class="swipe_img1">
          <p>#蛋糕和好身材你都要?</p><br>
          <i>让椰香代餐糕满足你</i>
        </div>
        <div>
          <img src="../assets/index/tuijian2.png" alt="" class="swipe_img1">
          <p>#一瓶抵一餐</p><br>
          <i>控卡有方 代餐奶昔</i>
        </div>
        <div>
          <img src="../assets/index/tuijian3.png" alt="" class="swipe_img1">
          <p>#来碗清香瘦肉粥</p><br>
          <i>五分钟get美味早餐</i>
        </div>
        <div>
          <img src="../assets/index/tuijian4.png" alt="" class="swipe_img1">
          <p>#嘿！来点低脂甜点吧</p><br>
          <i>燃一下很快乐！</i>
        </div>
      </div>
    </div>
    <!-- 推荐栏结束 -->
    <!-- 面板结束 -->
    <!-- 底部导航开始 -->
     <mt-tabbar v-model="active" fixed >
            <mt-tab-item id="index">
                首页
                <img src="../assets/me/index_active.png" slot="icon" v-if="active=='index'">
                <img src="../assets/me/index.png" slot="icon" v-else>
            </mt-tab-item>
            <mt-tab-item id="discover">
                贴吧
                <img src="../assets/me/discover_active.png" slot="icon" v-if="active=='discover'">
                <img src="../assets/me/discover.png" slot="icon" v-else>
            </mt-tab-item>
            <mt-tab-item id="jia">
                <img src="../assets/me/jia_active.png" slot="icon" v-if="active=='jia'">
                <img src="../assets/me/jia.png" slot="icon" v-else>
            </mt-tab-item>
            <mt-tab-item id="shopping">
                商城
                <img src="../assets/me/shopping_active.png" slot="icon" v-if="active=='shopping'">
                <img src="../assets/me/shopping.png" slot="icon" v-else>
            </mt-tab-item>
            <mt-tab-item id="me">
                我的
                <img src="../assets/me/me_active.png" slot="icon" v-if="active=='me'">
                <img src="../assets/me/me.png" slot="icon" v-else>
            </mt-tab-item>
        </mt-tabbar>
    <!-- 底部导航结束 -->
  </div>
</template>
<style scoped>
/* 顶部导航开始 */
.header{
  background: #4fe0b5;
}
.header_input{
  height: 30px;
}
.header_input input{
  width: 200px;
  border-radius: 18px;
  border: 0;
  outline: 0;
  padding: 6px;
  padding-left: 20px;
}
.header_input_img{
  vertical-align: middle;
}
/* 顶部导航结束 */
/* 面板开始 */
/* 轮播图开始 */
.mint-swipe{
  width: 100%;
  height: 170px;
  margin: 0 auto;
  margin-top: 40px;
}
.swipe_img1{
  width: 100%;
  height: 170px;
  /* border-radius: 18px; */
}
/* 轮播图结束 */
/* 状态开始 */
.mianban{
  width: 90%;
  height: 240px;
  border: 1px solid rgb(241, 241, 241);
  box-shadow: 2px 2px 9px rgba(0, 0, 0, 0.067);
  margin: 0 auto;
  border-radius: 15px;
  margin-top: 15px;
}
.mint-navbar .mint-tab-item.is-selected{
  color:#4fe0b5;
  border-bottom-color:#4fe0b5 ;
}
.cont{
  padding:12px 0 0px 5px;
}
.cont div,.cont2 div{
  width: 85%;
  border-bottom: 1px solid rgb(226, 226, 226);
  padding: 15px;
}
.cont img{
  position: relative;
  top: 7px;
}
.cont div:last-child,.cont2 div:last-child{
  border: none;
}
.cont i{
  font-size:12px;
  color: rgb(100, 100, 100);
  margin:0 35px 0 12px;
}
.cont span{
  color: #000;
  margin-left:68px;
  font-size: 24px;
}
.cont2 i{
  font-size: 20px;
  bottom: 5px;
  color: rgb(100, 100, 100);
  margin: 10px 10px 10px 5px;
  color:#000;
}
.cont2 span{
  bottom: 5px;
  font-size:12px;
  color: rgb(100, 100, 100);
  margin:0 90px 0 12px;
}
.cont2 img{
  position: relative;
  top: 6px;
}
.cont3{
  font-size: 15px;
  margin-top: 22px;
  text-align: center;
  color: rgb(100, 100, 100);
}
.cont3 p{
  padding-top: 10px;
}
.btn{
  width: 80px;
  background-color: white;
  color: #4fe0b5;
  border-radius: 15px;
  border: 2px solid #4fe0b5;
  outline: 0;
  padding: 2px;
  display: block;
  margin: 0 auto;
  margin-top: 35px;
}
/* 状态结束 */
/* 推荐开始 */
.Dapush{
  width: 90%;
  box-shadow: 2px 2px 9px rgba(0, 0, 0, 0.067);
  margin: 0px auto;
  border-radius: 13px;
  margin-bottom: 90px;
  margin-top: 20px;
}
.Dapush_Da{
  margin: 13px;
}
.Dapush_div{
  width: 5px;
  height: 15px;
  background: #4fe0b5;
  float: left;
  margin: 0 5px 0 5px;
  border-radius: 20px;
}
.Dapush_p{ 
  font-size: 18px; 
}
.Dapush_img{
  display: flex;
  flex-wrap: wrap;
}
.Dapush_img>div>img{
  width: 142px;
  height: 120px;
  margin: 10px 13px;
}
.Dapush_img>div>p{
  font-size: 12px;
  color: rgb(100, 100, 100);
  margin:-5px 13px;
}
.Dapush_img>div>i{
  font-size: 15px;
  color: #000;
  position: relative;
  top: -5px;
  left: 12px;
}
/* 推荐结束 */
/* 签到开始 */
.mtpopup{
  background: url("../assets/index/qiandao_cg.jpg");
 text-align: center;
 border-radius: 25px;
  width: 320px;
  height: 290px;
  background-size: 100% 100%;
  border-radius: 25px;
}
.mtpopup_button{
  background: #ec9221;
  font-size: 17px;
  width: 111px;
  height: 142px;
  outline: none;
  border: 0;
  border-radius: 100px;
  color: #fff;
  margin-top: 47px;
  margin-left: -9px;
  letter-spacing: 4px;
}
.mtpopup>h1{
    margin-top: 12px;
    font-size: 15px;
    color: #aaa;
}
/* 签到结束 */
/* 面板结束 */
</style>
<script>
export default {
  data(){
    return {
       active:'index',
       active_1:'1',
       popupVisible:false,
    }
  },
  methods:{
    show_qiandao(){
      // 获取当前时间
      var date = new Date();
      // console.log(date);
      // 获取当前小时
      var hours=date.getHours();
      // console.log(hours);
      // 获取当前分
      var fen = date.getMinutes();
      // console.log(fen);
      // 获取当前秒
      var miao = date.getSeconds();
      // console.log(miao);
      // 将获取的时间转化为毫秒
      var haomiao = hours*60*60*1000 + fen * 60 * 1000 + miao * 1000;
      // console.log(haomiao);
      // 获取24小时的毫秒数
      var onlydate = 1000*60*60*24;
      // console.log(onlydate);
      //  获取当前时间距离凌晨0:00的毫秒数
      var linch = onlydate - haomiao;
      // console.log(linch);
      this.popupVisible = true;

       

      this.$store.commit("qiandaoed");
      localStorage.setItem("qiandao",true);

      this.$store.commit("qdnumed");
      localStorage.setItem("qdnum",parseInt(this.$store.state.qdnum));


      window.setTimeout(()=>{
        this.$store.commit("yiqd");
        localStorage.removeItem("qiandao",true);
      },linch);
    },
    queding(){
      this.popupVisible = false;
    },
  },
  // 更改body的背景颜色
  // beforeCreate() {
  //      document.querySelector('body').setAttribute('style', 'background:rgb(240, 240, 240)');
       
  // },
  watch:{
    active(value){
      switch(value){
        case "index":
          this.$router.push('/');
          break;
        case "discover":
          this.$router.push("/discover");
          break;
        case "jia":
          this.$router.push("/jia");
          break;
        case "shopping":
          this.$router.push("/shopping");
          break;
        case "me":
          this.$router.push("/me");
          break;
      }
    }
  }
    
}
</script>