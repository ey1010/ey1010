<template>
  <div>
      <mt-header class='header' title='动态详情' >
          <img src="../assets/details/prev.png" slot='left' style="width:32px;height:32px" alt="">
          <img src="image/gengduo.png" slot='right' alt="">
      </mt-header>
      <mt-tab-container class='cont-nav'>
          <mt-tab-container-item>
            <img src="../assets/details/weixin.a08e87f9.png" style="width:32px;height:32px"  alt="">
             <span v-text="nic" ></span>
            <span style="margin-left:17rem">关注</span>
          </mt-tab-container-item>
      </mt-tab-container>
      <mt-tab-container>
        <mt-tab-container-item>
            <span>{{text}}</span>
        </mt-tab-container-item>
      </mt-tab-container>
      <mt-tab-container>
        <mt-tab-container-item>
            <div class='contImg'>
            <img :src="cont" alt="" v-for="(cont,i) of imgArr" class='img' :key='i'>
            </div>
        </mt-tab-container-item>
      </mt-tab-container>
      <mt-tabbar class='tabbar'>
          <mt-tab-item>
              <input type="text" placeholder="添加评论..." class='input' />
          </mt-tab-item>
          <mt-tab-item>
              <img src="../assets/details/dz.png" v-if='dianzan' @click="dianzans"   alt="">
             <img src="../assets/details/dz1.png" v-else @click='dianzans1'   alt="">
              <span class='dz' v-text='dz'></span>
          </mt-tab-item>
          <mt-tab-item>
             <img src="../assets/details/sc.png" v-if='shouchang' @click='shouchangs'  alt="">
             <img src="../assets/details/sc1.png" v-else @click='shouchangs1'  alt="">
             <span class='sc' v-text='sc'></span>
          </mt-tab-item>
      </mt-tabbar>
  </div>
</template>

<script>
export default {
    data(){
        return{
            nic:'昵称',
            imgArr:[
                "../assets/details/(V(J}8`]]RY4MDTW6OTR]PS.jpg",
                "../assets/details/123.jpg",
                "../assets/details/IH3PY_IZO[ZE][153~5~{F4.jpg"],
            text:`Lorem ipsum dolor sit amet consectetur adipisicing 
          elit. Officiis quibusdam adipisci dignissimos
           distinctio velit doloribus explicabo minima
            rerum maiores, minus beatae tempore, ill
            o nobis commodi? Ducimus rerum quae pariatur quos?
            Lorem ipsum dolor sit amet consectetur adipisicing 
          elit. Officiis quibusdam adipisci dignissimos
           distinctio velit doloribus explicabo minima
            rerum maiores, minus beatae tempore, ill
            o nobis commodi? Ducimus rerum quae pariatur quos?
            Lorem ipsum dolor sit amet consectetur adipisicing 
          elit. Officiis quibusdam adipisci dignissimos
           distinctio velit doloribus explicabo minima
            rerum maiores, minus beatae tempore, ill
            o nobis commodi? Ducimus rerum quae pariatur quos?`,
            dz:31,
            sc:20,
            dianzan:true,
            shouchang:true
            
        }
    },
    mounted(){
        // this.axios.get(`/details?did=?`).then((result)=>{

        // })
    },
    methods:{
        dianzans(){
            this.dianzan=false;
            this.dz++;
            console.log(this.dz);
        },
        dianzans1(){
            this.dianzan=true;
            this.dz--;
        },
        shouchangs(){
            this.shouchang=false;
            this.sc++;
        },
        shouchangs1(){
            this.shouchang=true;
            this.sc--;
        },
    }
}
</script>

<style scoped>
    .cont-nav{
        height:60px;
    }
    .input{
        background:lightblue;
        border-radius: 20px;
        border:1px solid #FFF;
        height:30px;
        margin-left:1.2rem;
        outline: 0;
    }
    .img{
        width:32.66%;
        height:100px;
        border:1px solid #FFF;
    }
    .dz{
        font-size:1rem;
    }
    .sc{
        font-size:1rem;
    }
    .tabbar{
        background:#FFF;
    }
</style>