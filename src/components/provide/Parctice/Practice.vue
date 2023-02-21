<template>
  <div>
    <input type="text" v-model="inputText">
    <button @click="addList">添加</button>
  </div>
  <vueList v-for="item in list " :key="item.id" :text="item.name"></vueList>
</template>

<script setup>
import vueList from './components/vue-list.vue';
import { ref } from 'vue'
const inputText = ref('')
const list = ref([
  {id:1,name:'panel'},
  {id:2,name:'jony'}
])

const addList = () => {
  if(inputText.value){
    list.value.push({id:list.value.length+1,name:inputText.value})
  }
  console.log(list.value);
}
</script>

<style>

</style>