<script setup>
import { ref,reactive,onMounted } from 'vue'
const msg = ref({
  content:'vue3'
})
const obj = reactive({
  name:'~'
})

const emit = defineEmits(['changeMsg'])

const setMsg = ()=>{
  msg.value.content = 'hi panel'
  emit('changeMsg',msg.value.content)
}
const setName = ()=>{
  obj.name = 'panel'
}
// 挂载dom的生命周期函数
onMounted(()=>{
  const h1 = document.querySelector('h1')
  console.log(h1);
})
onMounted(()=>{
  const card = document.querySelector('.card')
  card.style.backgroundColor = 'blue'
})

//通过ref的方式取dom
const objName = ref(null)
const changeObjName=()=>{
  objName.value.innerHTML = 'ref修改'
}
defineExpose({changeObjName})

const props = defineProps({
  data:Number
})
</script>

<template>
  <h1 >{{ msg.content }}</h1>
  <div class="card">
    <button type="button" @click="setMsg"> {{ msg.content }}</button>
  </div>
  <div ref="objName">{{ obj.name }}</div>
  <button @click="changeObjName">set-name</button>
  <div>父组件传过来的数据：{{ data }}</div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
