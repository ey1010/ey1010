<template>
  <div>
    <!-- 头部导航栏开始 -->
    <div class="header" fixed>
      <router-link to="/shopping" class="header_a">
        <p>
          <img src="../assets/shopd/back.png" alt="">
        </p>
      </router-link>
      <div  class="header_nav">
            <div @click="Commodity" :style="sp" >商品</div>
            <div @click="shopd" :style="xq" >详情</div>
        </div>
      <div class="header_share_div" @click="sharePopup">
          <img src="../assets/shopd/share.png" alt="" class="header_share">
      </div>
    </div>
    <!-- 头部导航栏结束 -->
    <!-- 分享开始 -->
    <mt-popup  v-model="popupVisible" 
               position="bottom"  
               popup-transition="popup-fade" 
               modal="true"
               class="share_popup">
               <p>请选择分享平台</p>
           <div class="share_popup_div">
             <div><router-link to="#"><img src="../assets/shopd/pyq.png" alt=""><p>微信朋友圈</p></router-link></div>
             <div><router-link to="#"><img src="../assets/shopd/wx.png" alt=""><p>微信</p></router-link></div>
             <div><router-link to="#"><img src="../assets/shopd/xlwb.png" alt=""><p>新浪微博</p></router-link></div>
             <div><router-link to="#"><img src="../assets/shopd/QQkj.png" alt=""><p>QQ空间</p></router-link></div>
           </div>
           <mt-tabbar >
             <mt-tab-item >
               <p @click="tabbarPopu">取消</p>
             </mt-tab-item>
           </mt-tabbar>
    </mt-popup>
    <!-- 分享结束 -->
    <!-- 面板开始 -->
    <div v-show="commodity">
        <!-- 图片显示开始 -->
      <div>
        <mt-swipe :auto=4000 :showIndicators="true" class=" mint-swipe">
          <mt-swipe-item class="mint-swipe-item">
            <img src="../assets/shopd/2.jpg" alt="" class="swipe_img1">
          </mt-swipe-item>
          <mt-swipe-item class="mint-swipe-item">
            <img src="../assets/shopd/3.jpg" alt="" class="swipe_img1">
          </mt-swipe-item>
          <mt-swipe-item class="mint-swipe-item">
            <img src="../assets/shopd/4.jpg" alt="" class="swipe_img1">
          </mt-swipe-item>
          <mt-swipe-item class="mint-swipe-item">
            <img src="../assets/shopd/5.jpg" alt="" class="swipe_img1">
          </mt-swipe-item>
        </mt-swipe>
      </div>
      <!-- 图片显示结束 -->
      <!-- 价格div开始 -->
      <div class="price">
        <p class="price_p">￥88 <span>  ￥128</span> </p>
        <h1>梨形身材变变变 | Easy Ace 血橙咖啡液 10袋/盒<span>人气热卖</span></h1>
        <div class="xiaoshou">
          <p>累计销量 5.2W+
            <span>由瘦吧官方自营店发货</span>
          </p>
        </div>
      </div>
      <!-- 价格div结束 -->
      <!-- 服务开始 -->
      <div class="fw_div">
        <p class="fw">服务</p>
        <p class="tuihuo">支持7天无理由退货</p>
      </div>
      <!-- 服务结束 -->
    </div>
    <div v-show="details">
        <div class="tupian">
          <img src="../assets/shopping/01.jpg" alt="">
          <img src="../assets/shopping/02.jpg" alt="">
          <img src="../assets/shopping/03.jpg" alt="">
          <img src="../assets/shopping/04.jpg" alt="">
          <img src="../assets/shopping/05.jpg" alt="">
          <img src="../assets/shopping/06.jpg" alt="">
          <img src="../assets/shopping/07.jpg" alt="">
          <img src="../assets/shopping/08.jpg" alt="">
          <img src="../assets/shopping/09.jpg" alt="">
          <img src="../assets/shopping/07.jpg" alt="">
        </div>
    </div>
    <!-- 面板结束 -->
    <!-- 底部开始 -->
    <div class="dibu">
      <div class="dibu_div">
        <img class="dibu_div_img" src="../assets/shopping/gouwuche.png" alt="">
      </div>
      <div class="dibu_div2">
        <img class="dibu_div2_img" src="../assets/shopping/kefu.png" alt="">
      </div>
      <div>
        <div class="dibu_div3">
          <p>加入购物车</p>
        </div>
      </div>
      <div  class="dibu_div4">
        <p>立即购买</p>
      </div>
    </div>
    <!-- 底部结束 -->
  </div>
</template>
<style scoped>
.tupian{
  margin-top: 40px;
}
.tupian>img{
  width: 100%;
  height: 416px;
}
.dibu{
  display: flex;
  color: #fff;
}
.dibu_div_img{
  width: 30px;
  height: 30px;
  margin-top: .3rem;
  margin-left: .5rem;  
}
.dibu_div2_img{
  width: 30px;
  height: 30px;
  margin-top: .3rem;
  margin-left: 2rem;
}
.dibu_div3{
  width: 150px;
  height: 40px;
  background-color: #45afec;
  margin-left: 1rem;
  text-align: center;
}
.dibu_div3>p{
  padding-top: 1rem;
 
}
.dibu_div4{
  width: 150px;
  height: 40px;
  background-color: #f7e11f;
  
  text-align: center;
}
.dibu_div4>p{
   margin-top: 1rem;
}
/* 头部header开始 */
.header{
  width: 100%;
  height: 2.5rem;
  background-color: #fff;
  position: fixed;
  top: 0rem;
}
.header_a{
  width: 10%;
  height: 2.5rem;
  display: block;
  float: left;
}
.header>a>p{
  line-height: 3.2rem;
  margin-left: 0.3rem;
}
.header_nav{
    background-color: #fff;
    color: rgb(172, 151, 151);
    margin-left: 100px;
    float: left;
    display: flex;
    margin-top: 1rem;
}
.header_nav>div+div{
  margin-left: 1.2rem;
}
.header_nav>div:active {
  color: #000;
}
.mint-navbar .mint-tab-item.is-selected{
  color: black;
}
.header_share_div{
  height: 2.5rem;
  margin-left: 21rem;
  line-height: 3.5rem;
}
.header_share_div>img{
  line-height: 3.2rem;
}
/* 头部header结束 */
/* 分享开始 */
.share_popup{
  width: 100%;
  height: 140px;
  background-color: rgb(235, 238, 243);
  text-align: center;
}
.share_popup>p{
  margin-top: 0.5rem;
}
.share_popup_div{
  display: flex;
  margin-top: 1.5rem;
}
.share_popup_div>div{
  margin-left: 2.4rem;
}
.share_popup_div>div>a>p{
  color: black;
  font-size: 0.5rem;
}
/* 分享结束 */
/* 轮播图开始 */
.mint-swipe{
  width: 100%;
  height: 350px;
  margin-top: 40px;
}
.swipe_img1{
  width: 100%;
  height: 350px;
}
/* 轮播图结束 */
/* 价格开始 */
.price,.fw_div{
  border-bottom: 1px solid rgba(142, 123, 141, 0.45);
}
.price_p{
  margin-top: 18px;
  color: red;
  font-size: 1.5rem;
}
.price_p>span{
  color: #aaa;
  font-size: 0.9rem;
  text-decoration: line-through;
  margin-left: 5px;
}
.price>h1{
  margin-top: 14px;
  font-size: 1.1rem;
  font-weight: 600;
}
/* 价格结束 */

/* 产品名称开始 */
.xiaoshou{
  font-size: 13px;
  margin: 20px 0 15px 0;
  font-weight: 100;
}
.xiaoshou span{
  margin-left: 125px;
}
/* 产品名称结束 */
/* 服务开始 */
.fw{
  font-size: 1.1rem;
  font-weight: 600;
  margin-top: 14px;
}
.tuihuo{
  font-size: 13px;
  font-weight: 100;
  margin: 14px 0 15px 0;
}
/* 服务结束 */
.dibu{
  width: 100%;
  height: 40px;
  background-color: #fff;
  /* margin-top: 22px; */
  position: fixed;
  top: 39.1rem;
}
</style>
<script>
export default {
  data(){
    return{
      popupVisible:false,
      commodity:true,
      details:false,
      sp:"color:rgb(0, 0, 0)",
      xq:"color:rgb(172, 151, 151)"
    }
  },
  methods:{
    sharePopup(){
      this.popupVisible=true;
    },
    tabbarPopu(){
      this.popupVisible=false;
    },
    Commodity(){
      this.commodity=true,
      this.details=false,
      this.sp = "color:#000",
      this.xq = "color:rgb(172, 151, 151)"
    },
    shopd(){
      this.commodity=false,
      this.details=true,
      this.xq = "color:#000",
      this.sp = "color:rgb(172, 151, 151)"
    }
  }
}
</script>