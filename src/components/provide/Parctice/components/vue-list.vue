<template>
  <div>{{ text }}</div>
</template>
<script setup>
defineProps({
    text:{
        type:String,
        defalut:''
    }
})
</script>
<style scoped>
div{
    height: 30px;
    line-height: 30px;
    border:1px solid #000;
}

</style>