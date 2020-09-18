<template>
    <div>
      <mt-header class="sh_dh" fixed>
        <div class="daohang" slot="left"> 
          <router-link to="/search">
            <img src="../assets/index/sousuo.png" alt=""  class="sh_sousuo"> 
            <input type="text" name="" id="" placeholder="搜索食品"> 
          </router-link>
        </div>
        <div slot="right" class="sh_img">
          <router-link to="/">
            <img src="../assets/shopping/gouwuche.png" alt="">
            <img src="../assets/shopping/xiaoxi.png" alt="">
          </router-link>
        </div> 
      </mt-header>
      <div class="datu_fu">
        <!-- 大图开始 -->
        <div >
          <img src="../assets/shopping/1.jpg" alt="" class="datu" >
        </div>
        <!-- 大图结束 -->

        <!-- 轮播图开始 -->
    <div>
      <mt-swipe :auto=4000 :showIndicators="true" class=" mint-swipe">
        <mt-swipe-item class="mint-swipe-item">
          <img src="../assets/shopping/2.jpg" alt="" class="swipe_img1">
        </mt-swipe-item>
        <mt-swipe-item class="mint-swipe-item">
          <img src="../assets/shopping/3.jpg" alt="" class="swipe_img1">
        </mt-swipe-item>
        <mt-swipe-item class="mint-swipe-item">
          <img src="../assets/shopping/4.jpg" alt="" class="swipe_img1">
        </mt-swipe-item>
        <mt-swipe-item class="mint-swipe-item">
          <img src="../assets/shopping/5.jpg" alt="" class="swipe_img1">
        </mt-swipe-item>
      </mt-swipe>
    </div>
    <!-- 轮播图结束 -->
    <!-- 小图标开始 -->
    <div class="shopping_xtb">
      <div><router-link to="/">
        <img src="../assets/shopping/gouwu.png" alt="">
        <p>新品购</p>
      </router-link>
    </div>
      <div  class="shopping_xtb_div">
        <router-link to="/">
          <img src="../assets/shopping/shiwu.png" alt="">
          <p>控卡主食</p>
        </router-link>
      </div>
      <div  class="shopping_xtb_div">
        <router-link to="/">
          <img src="../assets/shopping/shiwu2.png" alt="">
          <p>轻卡小食</p>
        </router-link>
      </div>
      <div  class="shopping_xtb_div">
        <router-link to="/">
          <img src="../assets/shopping/shoushen.png" alt="">
          <p>瘦瘦瘦瘦</p>
        </router-link>
      </div>
      <div  class="shopping_xtb_div">
        <router-link to="/">
          <img src="../assets/shopping/ranzhi.png" alt="">
          <p>助力燃脂</p>
        </router-link>
      </div>
      <div>
        <router-link to="/">
          <img src="../assets/shopping/tiaozhan.png" alt="">
          <p>10斤挑战</p>
        </router-link>
      </div>
      <div  class="shopping_xtb_div">
        <router-link to="/">
          <img src="../assets/shopping/bichi.png" alt="">
          <p>减肥必吃</p>
        </router-link>
      </div>
      <div  class="shopping_xtb_div">
        <router-link to="/">
          <img src="../assets/shopping/chanpin.png" alt="">
          <p>爱护身体</p>
        </router-link>
      </div>
      <div  class="shopping_xtb_div">
        <router-link to="/">
          <img src="../assets/shopping/changwei.png" alt="">
          <p>呵护肠胃</p>
        </router-link>
      </div>
      <div  class="shopping_xtb_div">
        <router-link to="/">
          <img src="../assets/shopping/gengduo.png" alt="">
          <p>更多</p>
        </router-link>
      </div>
    </div>
    <!-- 小图标结束 -->
    <!-- 中间夹着的一张图片 -->
      <div class="zhongjian">
        <img src="../assets/shopping/6.jpg" alt="" class="zhongjian_img">
      </div>
    <!-- 中间夹着的一张图片结束 -->
    <!-- 人气推荐开始 -->
    <div class="tuijian">
      <p>人气推荐</p>
    </div>
    <!-- 人气推荐结束 -->
    <!-- 商品页开始 -->
    <div class="shopping">
        <div class="shopping_div" v-for="i of 4" :key="i">
          <router-link to="/shoppingdetails">
            <img src="../assets/shopping/7.jpg" alt="" class="shopping_div_a_img">
            <p class="shopping_div_p1">好眠好身材<span class="shopping_div_p1_span">人气热卖</span></p>
            <p  class="shopping_div_p2">Easy Ace 血橙咖啡液  10袋/盒</p>
            <p  class="shopping_div_p3">￥189
              <span class="shoppping_div_span">已售 5.3w+</span>
            </p>
            
          </router-link>
        </div>
        <div class="end">
          <p>已经到底啦 ~_~</p>
        </div>
    </div>
    <!-- 商品页结束 -->
    </div>
      <tabbar :selected="selected"></tabbar>
    </div>
</template>
<style scoped>
/* 顶部导航开始 */
.sh_dh{
  background: #4fe0b5;
  width: 99%;
  position: fixed;
}
.sh_sousuo{
  /* height: 30px; */
  vertical-align: middle;
}
.daohang input{
  width: 200px;
  border-radius: 18px;
  border: 0;
  outline: 0;
  padding: 6px;
  padding-left: 20px;
}
.sh_img>a>img{
  padding: 2px;
}
/* 顶部导航结束 */
/* 大图 */
.datu{
    width: 100%;
    height: 223px;
    margin-top: 2.6rem;
}
/* 大图 */
/* 轮播图开始 */
.mint-swipe{
  width: 92%;
  height: 100px;
  margin: 5px auto;
  border-radius: 14px;
}
.mint-swipe-item>img{
  width: 100%;
  height: 110px;
}
/* 轮播图结束 */
/* 小图标开始 */
.shopping_xtb{
  width: 90%;
  height: 100px;
  display: flex;
  flex-wrap: wrap;
  margin: 0px auto;
}
.shopping_xtb>div{
  width: 55px;
  text-align: center;
}
.shopping_xtb_div{
  margin-left: 15px;
}
.shopping_xtb>div>a>img{
  width: 80%;
}
.shopping_xtb>div>a>p{
  font-size: 13px;
}
/* 小图标结束 */
/* 中间夹着的图片开始 */
.zhongjian{
    width: 92%;
    height: 100px;
    margin: 45px auto;
}
.zhongjian_img{
  width: 100%;
  height: 100px;
  border-radius: 14px;
}
/* 中间夹着的图片结束 */
/* 人气推荐开始*/
.tuijian{
  width: 90%;
  margin-left: 19px;
  color: #000;
  margin-top: -17px;
}
/* 人气推荐结束*/
/* 商品页开始 */
.shopping{
  width: 97%;
  height: 480px;
  margin: 16px auto;
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 218px;
}
.shopping_div{
  width: 45%;
  margin-left: 12px;
}
.shopping_div_a_img{
 width: 100%;
 height: 200px;
 border-radius: 10px;
}

.shopping_div_p1{
  font-weight: 900;
  font-size: 16px;
  color: #000;
  margin-top: 10px;
}
.shopping_div_p1_span{
  font-size: 11px;
  color: rgb(255, 255, 255);
  background-color: #fdec2f;
  border-radius: 20px;
  padding: 2px 2px;
  margin:6px;
}
.shopping_div_p2{
  font-weight: 100;
  font-size: 10px;
  margin-top:11px;
  letter-spacing: 1px;
}
.shopping_div_p3{
    font-weight: 100;
    font-size: 16px;
    color: red;
    margin: 10px 0 12px 0;
}
.shoppping_div_span{
  font-size: 10px;
  font-weight: 100;
  margin-left: 55px;
  color: #000;
}
.end{
  margin: 12px auto;
  font-weight: 100;
  font-size: 14px;
}
/* 商品页结束 */
</style>
<script>
import Tabbar from '../components/Tabbar.vue';
export default {
    components:{
    Tabbar
  },
    data(){
        return{
            selected:"shopping"
        }
    }
}
</script>