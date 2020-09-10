<template>
  <div>
    <!-- 上方背景图 -->
      <mt-header class="bg">
        <div slot="left" class="touxiang">
          <img src="../assets/touxiang.jpg" alt="">
        </div>
      </mt-header>
      <tabbar :selected="selected"></tabbar>
  </div>
</template>
<style scoped>
  
  .bg{
    height: 180px;
    background-color:pink;
  }
  .touxiang{
    margin:15px 10px ;
  }
  .touxiang img{
     border-radius: 100%;
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
            selected:'me'
        }
    },
    watch:{
        //监听底部选项卡的变化
        selected (value) {
            switch(value){
                case 'index':
                    this.$router.push('/').catch(()=>{});
                    break;
                case 'tieba':
                    this.$router.push('/tieba').catch(()=>{});
                    break;
                case 'jia':
                    this.$router.push('/jia').catch(()=>{});
                    break;
                case 'store':
                    this.$router.push('/store').catch(()=>{});
                    break;
                case 'me':
                    this.$router.push('/me').catch(()=>{});
                    break;
            }
        }
    }
}
</script>