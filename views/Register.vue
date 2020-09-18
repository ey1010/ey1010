<template>
  <div>
    <!-- 顶部导航开始 -->
    <div fiexd class="register-nav register-hairline-bottom" style="z-index:1">
      <div class="register-nav-left">
        <i class="register-icon register-icon-arrow-left register-nav_arrow"></i>
        <span class="register-nav-left-text">
          <router-link to="/">返回</router-link>
        </span>
      </div>
      <div class="register-nav-right">
        <span class="register-nav-left-text">
          <router-link to="/login">一键登录</router-link>
        </span>
      </div>
    </div>
    <!-- 顶部导航结束 -->
    <!-- 内容区域开始 -->
    <div class="content">
      <div class="content-main content-item">
        <span>手机号登陆/注册</span>
        <p>定制你的饮食方案，一站建立健康档案</p>
      </div>
    </div>
    <!-- 内容区域结束 -->
    <!-- form表单开始 -->
    <div class="form">
      <div class="form-main">
        <mt-field type="tel" label="手机号" placeholder="请输入手机号" disableClear :state="phoneState" :attr="{minlength:'11',maxlength:'11'}"
          v-model="phone"
          @blur.native.capture="checkPhone">
        </mt-field>
        <mt-field type="text" label="用户名" placeholder="请输入用户名" :state="usernameState" :attr="{minlength:'6',maxlength:'12'}"
          v-model="username"
          @blur.native.capture="checkUsername">
        </mt-field>
        <mt-field type="password" label="密 码" placeholder="请输入密码" disableClear :state="passwordState" :attr="{minlength:'6',maxlength:'20',autocomplate:'off'}"
          v-model="password"
          @blur.native.capture="checkPassword">
        </mt-field>
        <mt-field type="password" label="确认密码" placeholder="请再次输入密码" disableClear :state="password2State" :attr="{minlength:'6',maxlength:'20',autocomplate:'off'}"
          v-model="password2"
          @blur.native.capture="checkPassword2">
        </mt-field>
      </div>
    </div>
    <!-- form表单结束 -->
    <!-- 提交按钮开始 -->
    <button @click="handle" class="btn-lg tbody-button tbody-button--primary tbody-button--normal margin">
      <span class="tbody-button_title">注册</span>
    </button>
    <!-- 提交按钮结束 -->
  </div>
</template>
<script>
export default {
  data(){
    return {
      phone:'',
      username:'',
      password:'',
      password2:'',
      phoneState:'',
      usernameState:'',
      passwordState:'',
      password2State:'',
      selcArr:[],
      uphone1:[],
      uname1:[],
    }
  },
  mounted(){
    this.axios.get('/select').then((result)=>{
      this.selcArr=result.data;
      for(var key in this.selcArr){
        this.uphone1.push(this.selcArr[key].phone);
        this.uname1.push(this.selcArr[key].uname);
      }
    })
  },
  methods:{
    checkPhone(){
      let phoneRegExp=/^1[0-9]\d{9}$/;
      if(phoneRegExp.test(this.phone)){
        for(var key in this.uphone1){
        if(this.phone==this.uphone1[key]){
          this.$toast({
          message:"该手机号已注册",
          position:"middle",
          duration:4000
        });
        this.phoneState="error";
        }else{
          this.phoneState="success";
        }
      }
      }else{
        this.phoneState="error";
        this.$toast({
          message:"请输入正确的手机号",
          position:"middle",
          duration:4000
        });
      }
    },
    checkUsername(){
      let usernameRegExp=/^[a-zA-Z0-9_]{6,12}$/;
      if(usernameRegExp.test(this.username)){
        for(var key in this.uname1){
        if(this.username==this.uname1[key]){
          this.$toast({
          message:"用户名已存在",
          position:"middle",
          duration:4000
        });
        this.usernameState ="error";
        }else{
          this.usernameState="success";
        }
      }
      }else{
        this.usernameState ="error";
        this.$toast({
          message:"用户在6-12位之间",
          position:"middle",
          duration:4000
        });
      }
    },
    checkPassword(){
      let passwordRegExp=/^[a-zA-Z0-9]{6,9}$/;
      if(passwordRegExp.test(this.password)){
        
        this.passwordState ="success";
      
      }else{
        this.passwordState ="error";
        this.$toast({
          message:"密码在6-9位之间",
          position:"middle",
          duration:4000
        });
      }
        },
    checkPassword2(){
      if(this.password == this.password2){
        this.password2State ="success";
        return true;
      }else{
        this.password2State ="error";
        this.$toast({
          message:"两次输入不一致",
          position:"middle",
          duration:4000
        });
        return false;
      }
    },
    handle(){
      if(this.usernameState=="success"&&this.passwordState=="success"&&this.phoneState=="success"){

      this.axios.post('/reg',
        `&uname=${this.username}&upwd=${this.password}&phone=${this.phone}
      `).then((result)=>{
        if(result.data==1){
            this.$router.push("/");
            this.$messagebox("注册提示","注册成功");
        }else{
          this.$messagebox("注册提示","注册失败");
        }
        
      })
      }
    }
    },
}
</script>
<style scoped>
/* 顶部导航开始 */
.register-nav{
  position: relative;
  height: 45px;
  line-height: 45px;
  text-align: center;
  background-color: #fff;
  user-select: none;
  border-bottom: 0.5px solid #ccc;
}
.register-hairline-bottom::after{
  border-bottom-width: 1px;
}
.register-nav-left{
  left: 16px;
}
.register-nav-left, .register-nav-right{
  position: absolute;
  font-size: 14px;
  bottom: 0;
}
.register-icon{
  position: relative;
  width: 16px;
  height: 16px;
  font: 14px/1 header-icon;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  background: url(../assets/images/header_back.png) no-repeat;
}
.register-nav .register-icon{
  color: #1989fa;
  vertical-align: middle;
}
.register-nav_arrow{
  min-width: 1em;
  font-size: 16px;
}
.register-icon, .header-icon:before{
  display: inline-block;
}
.register-nav-left-text{
  display: inline-block;
  color: #1989fa;
  padding: 0 16px;
  margin: 0 -16px;
  vertical-align: middle;
}
.register-nav_arrow+ .register-nav-left-text{
  padding-left: 28px;
  margin-left: -25px;
}
.register-nav-left-text a{
 text-decoration: none; 
 font-size:16px;
  color: #1989fa;
  letter-spacing: 1px;
}
.register-nav-right{
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

/* form表单开始 */
.form{
  background-color: #fff;
}
.form-main{
  width: 95%;
  margin-left: 3%;
  padding-top: 19px;
}
/* form表单结束 */

/* 提交按钮开始 */
.btn-lg{
  width: 95%;
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
.tbody-button_title{
  letter-spacing: 1px;
}
.margin{
  margin-left:.4rem;
}
/* 提交按钮结束 */
</style>