<template>
  <div class="content">
    这里是中间组件
    <inject></inject>
  </div>
</template>
<script setup>
import inject from './components/inject.vue';
</script>
<style scoped>
.content{
    border: 1px solid #000;
}
</style>