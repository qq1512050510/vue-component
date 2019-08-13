<template>
    <div>
        <h2>这是一个头部组件{{title}}</h2>
        <button @click="func('123')">测试父组件方法</button>
    </div>
</template>
<script>
export default {
    data(){
        return {
            msg:"头部"
        }
    },
    props:['title','func'],
    mounted() {
    },
    
}
</script>

