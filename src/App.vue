<script setup>
import HelloWorld from './components/HelloWorld.vue'
import ComputedTest from './components/ComputedTest.vue';
import WatchTest from './components/WatchTest.vue';
import { ref } from 'vue';

const HW = ref(null)
const handle = ()=>{
  HW.value.changeObjName()
}
const onMsgChange = (v) => {
  console.log('子组件触发事件，发过来的数据为：',v);
}
</script>

<template>
  <HelloWorld ref="HW" :data="333" @change-msg="onMsgChange" />
  <ComputedTest></ComputedTest>
  <WatchTest></WatchTest>
  <button @click="handle">调用子组件函数</button>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
