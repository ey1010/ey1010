<template>
  <div>
    <!-- 上方背景图 -->
      <div class="bg">
        <div class="touxiang">
          <router-link to="/information">
            <img src="../assets/me/touxiang.jpg" alt="">
          </router-link>
        </div>
        
        <!-- 昵称 -->
        <div class="user">
          <!-- 注册登录 -->
        <div  v-if="!this.$store.state.login">
          <router-link to="/login">登录</router-link> | 
          <router-link to="/register">注册</router-link>
        </div>
        <!-- 注册登录结束 -->
          <div v-else>
            <p>
            <router-link to="/information">BH85933907</router-link>
          </p>
          <p>
            <router-link to="/information">我的宣言：请填写</router-link>
          </p>
          </div>
        </div>

        <div class="item">
          <div class="item-i">
            <p class="i">动态</p>
            <p class="i">关注</p>
            <p class="i">粉丝</p>
          </div>
          <div class="item-l">
            <p class="l">0</p>
            <p class="l">0</p>
            <p class="l">0</p>
          </div>
        </div>
      </div>
      <!-- 中间选项卡 -->
      <div class="ka">
        <div class="ka-item" >
          <router-link to="/order">
            <img src="../assets/me/dingdan.png" alt="">
          </router-link>
          <router-link to="/order">
            <img src="../assets/me/gouwu.png" alt="">
          </router-link>
          <router-link to="/order">
            <img src="../assets/me/dizhi.png" alt="">
          </router-link>
          <router-link to="/shopping">
            <img src="../assets/me/shiwu.png" alt="">
          </router-link>
          <router-link to="/">
            <img src="../assets/me/shoucang.png" alt="">
          </router-link>
        </div>
        <div class="ka-text" >
          <router-link to="/order">订单</router-link>
          <router-link to="/order">购物车</router-link>
          <router-link to="/me">收获地址</router-link>
          <router-link to="/me">食物库</router-link>
          <router-link to="/me">收藏</router-link>
        </div>
      </div>
      <!-- 中间2选项卡 -->
      <div class="nav">
        <mt-cell title="设置" isLink class="nav_item">
          <img src="../assets/me/sehzhi.png" slot="icon">
        </mt-cell>
        <mt-cell title="意见反馈" isLink>
          <img src="../assets/me/yijian.png" slot="icon">
        </mt-cell>
        <mt-cell title="隐私声明" isLink>
          <img src="../assets/me/yinsi.png" slot="icon">
        </mt-cell>
        <mt-cell title="版本更新" isLink>
          <img src="../assets/me/banben.png" slot="icon">
        </mt-cell>
        <mt-cell title="退出登录" isLink class="nav_item1">
          <img src="../assets/me/tuichu.png" slot="icon">
        </mt-cell>
      </div>
      <!-- 底部选项卡 -->
      <tabbar :selected="selected"></tabbar>
  </div>
</template>
<style scoped>
  .bg{
    height: 230px;
    /* background-color: #F4A460; */
    /* background-color:#fa8072; */
    background-color: #4fe0b5;
    /* background-color: #00c4b3; */

  }
  .bg .touxiang{
    width: 65px;
    height: 65px;
    padding:50px 0 0 15px;
  }
  .touxiang img{
     border-radius: 100%;
  }
  .user{
    text-align: left;
    margin: 0;
    position: relative;
  }
  .user a{
    text-decoration: none;
    color:#fff;
    letter-spacing: 0.1rem;
    opacity: 0.9;
  }
  .user{
    margin: -50px 0 0 95px;
  }
  .user p:first-child a{
    font-size: 16px;
  }
  .user p:last-child a{
    font-size: 12px;
  }
  .user p:last-child{
    height:31px;
    overflow: hidden;
  }
  .user p:first-child{
    padding-bottom: 10px;
  }
  .item-i,.item-l{
    display: flex;
  }
  .item-i .i{
    color:#fff;
    margin: 0 auto;
    margin-top: 55px;
    font-size: 14px;
    opacity: 0.9;
  }
  .item .l{
    color: #fff;
    margin: 0 auto;
    margin-top: -36px;
  }
  .ka{
    width: 90%;
    background-color: #fff; 
    margin: 0 auto;
    margin-top: -17px;
    border-radius: 12px;
    box-shadow: 2px 2px 9px #1001;
  }
  .ka-item,.ka-text{
    display: flex;
    padding-top: 10px;
  }
  .ka-item>a{
    margin: 0 auto;
    position: relative;
  }
  .ka-text>a{
    color: #001010;
    font-size: 13px;
    margin: 0 auto;
    opacity: 0.9;
    margin-bottom: 15px;
  }
  .ka-item a:first-child{
    left: -4px;
  }
  .ka-item a:nth-child(2){
    left: -10px;
  }
  .ka-item a:last-child{
    right: -5px;
  }
  .ka-item a:nth-child(4){
    left: 8px;
  }
  .nav{
    width: 90%;
    background-color: #fff; 
    margin: 0 auto;
    border-radius: 20px;
    box-shadow: 2px 2px 9px  #e7e7e7;
    margin-top: 24px;
  }
  .nav img{
    margin: 0 4px 0 2px;
  }
  .nav_item{
    border-top-left-radius:15px;
    border-top-right-radius:15px;
  }
  .nav_item1{
    border-bottom-left-radius:15px;
    border-bottom-right-radius:15px;
  }
</style>
<script>
import Tabbar from '../components/Tabbar.vue';
export default {
  components:{
        Tabbar
    },
    data(){
        return{
            //默认被选定的底部选项卡
            selected:'me',
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
    },
    methods:{
      
    },
}
</script>