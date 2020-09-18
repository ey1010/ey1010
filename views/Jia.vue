<template>
  <div>
    <!-- 面板内容开始 -->
    <div class="jia">
      <div class="jia_eat">
        <router-link to="/">
          <img src="../assets/jia/eat.png" alt="">
          <p>记饮食</p>
        </router-link>
      </div>
      <div>
        <router-link to="/">
          <img src="../assets/jia/motion.png" alt="">
          <p>记运动</p>
        </router-link>
      </div>
      <div>
        <router-link to="/">
          <img src="../assets/jia/weight.png" alt="">
          <p>记体重</p>
        </router-link>
      </div>
      <div>
        <router-link to="/">
          <img src="../assets/jia/dynamic.png" alt="">
          <p>发动态</p>
        </router-link>
      </div>
    </div>
    <!-- 面板内容结束 -->
    <!-- 底部导航栏开始 -->
      <mt-tabbar fixed >
            <mt-tab-item>
              <router-link to="/">
                <img src="../assets/jia/X.png" alt="">
              </router-link>
            </mt-tab-item>
      </mt-tabbar>
    <!-- 底部导航栏结束 -->
  </div>
</template>
<style scoped>
.jia{
  /* background: aqua; */
  margin: 0 auto;
  display: flex;
  padding-top: 35rem;
  margin-bottom: 60px;
}
.jia>div{
  margin: 0 auto;
  margin-top: -35px;
}
.jia>div>a>img{
  margin-left: 7px;
}
.jia>div>a>p{
    color: #000;
}
</style>