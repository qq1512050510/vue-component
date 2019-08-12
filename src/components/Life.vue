<template>
    <div id="life">
        生命周期函数{{msg}}
        <button @click="changMsg()">改变MSG</button>
    </div>
</template>
<script>
export default {
    data(){
        return{
            msg:'这是一个生命周期函数组件'
        }
    },
    methods:{
        changMsg(){
            this.msg = "改变MSG值"
        }
    },
    beforeCreate(){
        console.log('实例创建之前')
    },
    created:function(){
        console.log('实例创建完成');
    },
    beforeMount(){
        console.log('模板挂载之前');
    },
    mounted(){
        console.log('模板编译完成');
    },beforeUpdate() {
        console.log('更新之前');
    },updated() {
        console.log('更新之后');
    },beforeDestroy() {
        console.log('销毁之前');
    },destroyed() {
        console.log('销毁之后');
    },
}
</script>
