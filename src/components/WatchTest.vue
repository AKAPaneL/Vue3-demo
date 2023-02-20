<template>
  输入<input type="text" v-model="value">
</template>
<script setup>
    import { ref, watch } from 'vue'
    const value =ref('')
    watch(value,()=>{
        console.log('数据正在改变:',value.value);
    },{
        deep:true
    })
</script>
<style>

</style>