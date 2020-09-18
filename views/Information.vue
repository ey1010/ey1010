<template>
  <div>
    <mt-header class="mtheader" title="个人信息">
      <router-link to="/me" slot="left">
        <mt-button icon="back"></mt-button>
      </router-link>
    </mt-header>
    <!-- 个人信息开始 -->
    <mt-cell title="头像" class="cell-text" isLink>
      <span><img class="txiang" src="../assets/Information/33333.jpg" slot="icon" alt=""></span>
    </mt-cell>
    <mt-cell title="用户名/昵称" class="cell-text" isLink><span>BH85933907</span></mt-cell>
    <mt-cell title="我的宣言" class="cell-text" isLink><span>请填写</span></mt-cell>
    <mt-cell title="手机号码" class="cell-text" isLink><span>已验证</span></mt-cell>
    <!-- 个人信息结束 -->

  </div>
</template>
<style scoped>
.mtheader{
  background-color: #4fe0b5;
}
.mtspan{
  margin-left:130px;
}
.cell-text{
  text-align: left;
  outline: 0;
}
.txiang{
  width: 35px;
  height: 35px;
  border-radius: 50%;
  background-size: cover;
}
</style>