<template>
    <div>
        <h2>主动获取传参</h2>
        <button @click="runParentFunc()">获取父组件值</button>
    </div>
</template>
<script>
export default {
    data(){
        return{
            msg:"主动传参"
        }
    },methods:{
        run(){
            alert("HeaderActive");
        },
        runParentFunc(){
            console.log(this.$parent);
            alert(this.$parent.msg);
        }
    }
}
</script>

