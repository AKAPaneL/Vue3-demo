<script>
import { ref,reactive } from 'vue'
const count = ref(0)
export default {
  setup(){
    const msg = ref({
      id:'111111'
    })
    const obj = reactive({
      name:'panel'
    })
    const setMsg = ()=>{
      msg.value.id = 'hi panel'
    }
    const setName = ()=>{
      obj.name = 'p'
    }

    return { setMsg,msg,obj,setName }
    
  }
}
</script>

<template>
  <h1>{{ msg.id }}</h1>
  <div class="card">
    <button type="button" @click="setMsg"> {{ msg.id }}</button>
  </div>
  <div>{{ obj.name }}</div>
  <button @click="setName">set-name</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
