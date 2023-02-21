<template>
  <div class="content">
    这里是底层组件,注入的数据为：{{ data }}
  </div>
  <button @click="setdata">点击我修改数据</button>
</template>
<script setup>
import { inject } from 'vue'
const data = inject('provideData')
const setdata = inject('setProvideData')

</script>
<style scoped>
.content{
    border: 1px solid #000;
}
</style>