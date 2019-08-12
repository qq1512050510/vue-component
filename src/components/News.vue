<template>
    <div>
        <v-header></v-header>
        <h2>这是一个新闻组件</h2>
    </div>
</template>
<script>
import Header from './Header'
export default {
    data(){
        return{
            mesg:"",
        }
    },components:{
        'v-header':Header
    }
}
</script>
