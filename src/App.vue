<script setup>
import HelloWorld from './components/HelloWorld.vue'
import ComputedTest from './components/ComputedTest.vue';
import WatchTest from './components/WatchTest.vue';
import Provide from './components/provide/index.vue'
import Practice from './components/provide/Parctice/Practice.vue';
import { ref,provide } from 'vue';

const HW = ref(null)

const provideData = ref(123)
const setProvideData = () => {
  provideData.value = 789
}
const handle = ()=>{
  HW.value.changeObjName()
}
const onMsgChange = (v) => {
  console.log('子组件触发事件，发过来的数据为：',v);
}
provide('provideData',provideData)
provide('setProvideData',setProvideData)

</script>

<template>
  <HelloWorld ref="HW" :data="333" @change-msg="onMsgChange" />
  <ComputedTest></ComputedTest>
  <WatchTest></WatchTest>
  <button @click="handle">调用子组件函数</button>
  <div>app根实例:provide:{{ provideData }}</div>
  <Provide></Provide>
  <Practice/>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
</style>
