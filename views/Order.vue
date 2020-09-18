<template>
  <div>
    <!-- 导航栏开始 -->
    <mt-header fiexd title="我的订单" class="ordering-header">
      <router-link to="/me" slot="left">
        <mt-button icon="back"></mt-button>
      </router-link>
    </mt-header>
    <!-- 导航栏结束 -->
    <!-- 顶部选项卡开始 -->
    <mt-navbar v-model="active">
      <mt-tab-item >全部</mt-tab-item>
      <mt-tab-item class="order-container-h6">待付款</mt-tab-item>
      <mt-tab-item class="order-container-h6">待发货</mt-tab-item>
      <mt-tab-item class="order-container-h6">待收货</mt-tab-item>
      <mt-tab-item class="order-container-h6">待评论</mt-tab-item>
    </mt-navbar>
    <!-- 顶部选项卡结束 -->
    <!-- 面板区域开始 -->
    <div class="order-container">
      <mt-tab-container>
        <mt-tab-container-item class="order-container-item">
        <img src="../assets/order/orderIcon.png" alt="">
        <p>你还没有订单</p>
        <p>看到喜欢的就下手吧！</p>
        </mt-tab-container-item>
      </mt-tab-container>
    </div>
    <!-- 面板区域结束 -->
  </div>
</template>
<script>
export default {
  data(){
    return {
      active:1,
    }
  }
}
</script>
<style scoped>
.ordering-header{
  color: black;
  background-color: #fff;
}
.mint-navbar .mint-tab-item.is-selected{
  border-bottom: none;
  color: #000;
}
.order-container{
  background-color: rgb(248, 248, 248);
  height: 37rem;
}
.order-container-h6{
  color: #ccc;
}
.order-container-item img{
  margin-top: 15rem;
  margin-left: 10rem;
  text-align: center;
}
.order-container-item p{
  color: #ccc;
  font-size: 8px;
  margin-top: 5px;
  margin-left: 10rem;
}
.order-container-item p:nth-child(3){
  margin-left: 8.6rem;

}
</style>