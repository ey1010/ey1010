<template>
    <div>
        <!-- 底部选项卡 -->
        <mt-tabbar v-model="active" >
            <mt-tab-item id="index">
                首页
                <img src="../assets/me/index_active.png" slot="icon" v-if="active=='index'">
                <img src="../assets/me/index.png" slot="icon" v-else>
            </mt-tab-item>
            <mt-tab-item id="tieba">
                贴吧
                <img src="../assets/me/tieba_active.png" slot="icon" v-if="active=='tieba'">
                <img src="../assets/me/tieba.png" slot="icon" v-else>
            </mt-tab-item>
            <mt-tab-item id="jia">
                <img src="../assets/me/jia_active.png" slot="icon" v-if="active=='jia'">
                <img src="../assets/me/jia.png" slot="icon" v-else>
            </mt-tab-item>
            <mt-tab-item id="store">
                商城
                <img src="../assets/me/store_active.png" slot="icon" v-if="active=='store'">
                <img src="../assets/me/store.png" slot="icon" v-else>
            </mt-tab-item>
            <mt-tab-item id="me">
                我的
                <img src="../assets/me/me_active.png" slot="icon" v-if="active=='me'">
                <img src="../assets/me/me.png" slot="icon" v-else>
            </mt-tab-item>
        </mt-tabbar>
    </div>
</template>
<script>
export default {
    props:["selected"],
    data(){
        return{
            active:this.selected
        }
    },
    watch:{
        active(value){
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