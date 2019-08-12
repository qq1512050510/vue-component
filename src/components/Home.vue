<template>
    <!-- 所有的内容被根节点包含起来 -->
    <div>
        <v-header></v-header>
        <h2>{{msg}}</h2>
        <button v-on:click="run()">按钮</button>
        <v-life v-if="flag"></v-life>
        <button @click="flag=!flag">销毁life组件</button>
        <button @click="getData()">Vue-resource请求数据按钮</button>
        <button @click="getDataByAxios()">Vue-resource请求数据按钮</button>
        <ul>
            <li v-for="(item,key) in listData" :key="key">
                {{item}}
            </li>
        </ul>
    </div>
</template>
<script>
import Header from './Header'
import Life from './Life'
import Axios from 'axios'
export default {
    data(){
        return {
            msg:'我是一个首页组件',
            flag:true,
            listData:[]
        }
    },methods:{
        run(){
            alert(123);
        },
        getData(){
            var api = 'http://www.phonegap100.com/appapi.php?a=getPortalList&catid=20&page=1'
            this.$http.get(api).then(response=>{
                console.log(response);
              this.listData = response.body.result
            },error=>{
                console.log(error);
            })
        },
        getDataByAxios(){
            var api = 'http://www.phonegap100.com/appapi.php?a=getPortalList&catid=20&page=1'
            Axios.get(api)
            .then( (response)=>{
                // handle success
                console.log(response);
                this.listData = response.data
            })
            .catch( (error)=> {
                // handle error
                console.log(error);
            })
            .finally( ()=> {
                // always executed
            });
        }
    },components:{
        'v-header':Header,
        'v-life':Life
    },mounted() {
       // this.getData();
       this.getDataByAxios();
    },
}
</script>

<style scoped>
    h2{
        color:red
    }
    h1{
        color:blue
    }
</style>

