<template>
    <div>
        <v-header></v-header>
        <h2>这是一个新闻组件</h2>
    </div>
</template>
<script>
import Header from './Header'
import VueEvent from '../model/VueEvent'
export default {
    data(){
        return{
            msg:"测试",
        }
    },components:{
        'v-header':Header
    },mounted(){
        VueEvent.$on('to-news',function(data){
            alert("news组件");
            console.log(data);
        });
    }
}
</script>
