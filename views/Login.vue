<template>
  <div class="header">
    <!-- 顶部导航开始 -->
    <div class="header-nav header-hairline-bottom" style="z-index:1">
      <div class="header-nav-left">
        <i class="header-icon header-icon-arrow-left header-nav_arrow"></i>
        <span class="header-nav-left-text">
          <router-link to="/">返回</router-link>
        </span>
      </div>
      <div class="header-nav-right">
        <span class="header-nav-left-text">
          <router-link to="/register">注册</router-link>
        </span>
      </div>
    </div>
    <!-- 顶部导航结束 -->
    <!-- 标题区域开始 -->
    <div class="content">
      <div class="content-main content-item">
        <span>密码登陆</span>
        <p>定制你的饮食方案，一站建立健康档案</p>
      </div>
    </div>
    <!-- 标题区域结束 -->
    <!-- 登陆区域开始 -->
    <div class="tbody-group tbody-hairline-top-bottom">
      <div class="info-lg tbody-cell tbody-field">
        <div class="tbody-cell_title tbody-field_label">
          <span>
            <font style="vertical-align: inherit;">用户名</font>
          </span>
        </div>
      <div class="tbody-cell__value">
        <div class="tbody-field_body">
          <input type="text"  placeholder="用户名/手机号/邮箱" 
            :state="usernameState" 
            minlength="6" maxlength="12" 
            v-model="username" 
            class="tbody-field_input"
          />
        </div>
      </div>
      </div>
      <div class="info-lg tbody-cell">
        <div class="tbody-cell_title tbody-field_label">
          <span>
            <font style="vertical-align: inherit;">密码</font>
          </span>
        </div>
      <div class="tbody-cell__value">
        <div class="tbody-field_body">
          <input type="password" placeholder="请输入密码" 
            :state="passwordState" 
            minlength="8" maxlength="20" 
            autocomplete="off" 
            v-model="password" 
            class="tbody-field_input" />
        </div>
      </div>
      </div>
    </div>
    <!-- 登陆区域结束 -->
    <!-- 忘记密码开始 -->
    <div class="forget">
      <router-link to="/">忘记密码</router-link>
    </div>
    <!-- 忘记密码结束 -->
    <button @click="handle" class="btn-lg tbody-button tbody-button--primary tbody-button--normal margin">
      <span class="tbody-button_title">登陆</span>
    </button>
    <!-- 第三方账号 -->
    <div>
      <p class="party-main">
        <font style="vertical-align: inherit;">
          ———————第三方账号登陆———————
        </font>
      </p>
      <div>
        <router-link to="/login"><img src="../assets/images/qq.4f46fee1.png" alt="" class="icon-img"></router-link>
        <router-link to="/login"><img src="../assets/images/weixin.a08e87f9.png" alt="" class="icon-img"></router-link>
        <router-link to="/login"><img src="../assets/images/zhifubao.434259ce.png" alt="" class="icon-img"></router-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data(){
    return {
      username:"",
      password:"",
      usernameState:"",
      passwordState:"",
    }
  },
  methods:{

    handle(){
        this.axios.post("/login",`uname=${this.username}&&upwd=${this.password}`).then((res)=>{
          if(res.data == 0){
            this.$messagebox("登陆提示","用户名或密码错误");
            
          }else{
            this.$messagebox("登陆提示","登录成功");
            this.$router.push("/me");
            this.$store.commit("logined");
            localStorage.setItem("login",true);
          }
        });
      }
    },
  }

</script>
<style scoped>
/* 顶部导航开始 */
.header{
  height: 520px;
}
.header-nav{
  position: relative;
  height: 45px;
  line-height: 45px;
  text-align: center;
  background-color: #fff;
  user-select: none;
  border-bottom: 0.5px solid #ccc;

}
.header-hairline-bottom::after{
  border-bottom-width: 1px;
}
[class*=header-hairline]:after {
  position: absolute;
  box-sizing: border-box;
  content: " ";
  pointer-events: none;
  top: -50%;
  right: -50%;
  bottom: -50%;
  left: -50%;
  border: 0 solid #ebedf0;
  -webkit-transform: scale(.5);
  transform: scale(.5);
}
.header-nav-left{
  left: 16px;
}
.header-nav-left, .header-nav-right{
  position: absolute;
  font-size: 14px;
  bottom: 0;
}
.header-icon{
  position: relative;
  width: 16px;
  height: 16px;
  font: 14px/1 header-icon;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  background: url(../assets/images/header_back.png) no-repeat;
}
.header-nav .header-icon{
  color: #1989fa;
  vertical-align: middle;
}
.header-nav_arrow{
  min-width: 1em;
  font-size: 16px;
}
.header-icon, .header-icon:before{
  display: inline-block;
}
.header-nav-left-text{
  display: inline-block;
  color: #1989fa;
  padding: 0 16px;
  margin: 0 -16px;
  vertical-align: middle;
}
.header-nav_arrow+ .header-nav-left-text{
  padding-left: 28px;
  margin-left: -25px;
}
.header-nav-left-text a{
 text-decoration: none; 
 font-size:16px;
  color: #1989fa;
  letter-spacing: 1px;
}
.header-nav-right{
  right: 16px;
}
/* 顶部导航结束 */

/* 标题区域开始 */
.content{
  background-color: #fff;
}
.content-main{
  width: 90%;
  margin-left: 8%;
  padding-top: 45px;
}
.content-item{
  position: relative;
  overflow: hidden;
  line-height: 30px;
  text-align: left;
  letter-spacing: 1px;
}
.content-item span{
  font-size: 30px;
  font-weight: 500;
  color: #323233;
}
.content-item p{
  font-size: 17px;
  color: #aaa;
}
/* 标题区域结束 */

/* 登陆区域开始 */
.tbody-group{
  background-color: #fff;
  height: 100px;
}
.tbody-hairline-top-bottom{
  position: relative;
}
.info-lg{
  margin-top: 25px;
  margin-left: 7%;
  width: 85%;
  height: 35px;
  border-bottom: .5px solid #aaa;
}
.tbody-cell{
  position: relative;
  display: flex;
  overflow: hidden;
  color: #323233;
  font-size: 16px;
  line-height: 35px;
  background: #fff;
}
.tbody-cell:not(:last-child):after {
    position: absolute;
    box-sizing: border-box;
    content: " ";
    pointer-events: none;
    right: 0;
    bottom: 0;
    left: 16px;
    border-bottom: 1px solid #ebedf0;
    -webkit-transform: scaleY(.5);
    transform: scaleY(.5);
}
.tbody-cell__title,.tbody-cell__value{
    -webkit-box-flex: 1;
    -webkit-flex: 1;
    flex: 1;
}
.tbody-cell__title{
  margin-top: 3px;
}
.tbody-field_label{
  -webkit-box-flex: 0;
  width: 80px;
  height: 30px;
  flex: none;
  margin-top: 1px
}
.tbody-cell__value{
  position: relative;
  overflow: hidden;
  height: 30px;
  color: #969799;
  text-align: right;
  vertical-align: middle;
}
.tbody-field_body{
  margin-top: 3px;
  display: flex;
  width: 200px;
  align-items: center;
}
input{
  font: inherit;
}
.tbody-field_input{
  display: block;
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
  width: 100%;
  height: 30px;
  resize: none;
  color: #323233;
  text-align: left;
  box-sizing: border-box;
  background-color: transparent;
  outline: 0;
  letter-spacing: 1px;
}
/* 登陆区域结束 */

/* 忘记密码开始 */
.forget{
  background-color: #fff;
  width: 85%;
  margin-left: 7%;
  margin-top: 15px;
  text-align: right;
  font-size: 14px;
  color: #1989fa;
}
/* 忘记密码结束 */

/* 登陆按钮开始 */
.btn-lg{
  width: 85%;
  border: none;
  margin-top: 12%;
  border-radius: 24px;
}
.tbody-button{
  position: relative;
  display: inline-block;
  height: 42px;
  line-height: 42px;
  text-align: center;
  box-sizing: border-box;
  -webkit-appearance: none;
  outline: 0;
}
.tbody-button--primary {
    color: #fff;
    background-color: #07c160;
    border: 1px solid #07c160;
}
.tbody-button--normal{
  font-size: 14px;
  font-weight: 500;
  padding: 0 15px;
}
.margin{
  margin-left:1.7rem;
}
.tbody-button_title{
  letter-spacing: 1px;
}
/* 登陆按钮结束 */

/* 第三方账号开始 */
.party-main{
  height: 21px;
  line-height: 21px;
  margin-top: 25px;
}
a{
  text-decoration: none;
}
.icon-img{
  width: 30px;
  margin-right: 3%;
  margin-top: 7%;
}
/* 第三方账号结束 */
</style>