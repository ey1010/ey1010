<template>
  <div>
    <!-- 导航开始 -->
    <mt-header class="header" fixed>
     <div slot="right" id="header_img">
        <router-link to="/">取消</router-link>
     </div> 
     <div class="header_input" slot="left"> 
        <img src="../assets/index/sousuo.png" alt=""  class="header_input_img"> 
        <input type="text" name="" id="inputid" v-model="newid" placeholder="搜索食物"> 
     </div> 
   </mt-header>
    <!-- 导航结束 -->
    <!-- 面板开始 -->
    <div class="mianban">
      <router-link to="/">更多 ></router-link>
      <p>食物推荐榜单</p>
      <ul class="mianban_ul">
        <li> <router-link to="/">减肥</router-link></li>
        <li> <router-link to="/">增肌</router-link></li>
        <li> <router-link to="/">孕妇</router-link></li>
        <li> <router-link to="/">美白</router-link></li>
        <li> <router-link to="/">儿童生长</router-link></li>
        <li> <router-link to="/">糖尿病</router-link></li>
        <li> <router-link to="/">便秘</router-link></li>
      </ul>
    </div>
    <div class="mianban1">
      <p>大家都在搜</p>
      <ul class="mianban_ul1">
        <li> <router-link to="/">米饭</router-link> </li>
        <li> <router-link to="/">鸡蛋</router-link> </li>
        <li> <router-link to="/">苹果</router-link> </li>
        <li> <router-link to="/">橘子</router-link> </li>
        <li> <router-link to="/">牛奶</router-link> </li>
        <li> <router-link to="/">香蕉</router-link> </li>
      </ul>
    </div>
     <!-- 面板结束 -->
  </div>
</template>
<style scoped>
.header{
  background: #4fe0b5;
}
/* 顶部导航开始 */
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
.mianban{
  height: 160px;
  margin-top: 63px;
  font-size: 20px;
  font-weight: 600;
  margin-right: 10px;
}
.mianban>p{
  margin-left: 15px;
}
.mianban>a{
  color: rgb(151, 158, 158);
  font-size: 15px;
  font-weight: 300;
  float: right;
}
.mianban_ul>li{
  float: left;
  width: 80px;
  height: 30px;
  text-align: center;
  background: rgb(243, 243, 243);
  line-height: 30px;
  border-radius: 20px;
  margin-left: 20px;
  margin-top: 10px;
  font-size: 14px;
}
.mianban_ul>li>a,.mianban_ul1>li>a{
  color:rgb(90, 90, 90);
}
.mianban1{
  font-size: 20px;
  font-weight: 600;
  margin-left: 10px;
  margin-right: 10px;
}
.mianban1>p{
  margin-left: 5px;
}
.mianban_ul1>li{
  float: left;
  width: 80px;
  height: 30px;
  text-align: center;
   background: rgb(243, 243, 243);
  line-height: 30px;
  border-radius: 20px;
  margin-left: 5px;
  margin-top: 10px;
  font-size: 14px;
}
 
/* 面板结束 */


</style>
<script>
export default {
  data(){
    return{
      newid:''
    }
  },
  methods:{
     
  },
  mounted(){
    document.getElementById("inputid").focus();

  }
}
</script>