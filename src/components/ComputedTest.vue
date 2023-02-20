<template>
  <div>
    <dl>
        <dt>分数列表</dt>
        <dd v-for="item in scoreList">{{ item }}</dd>
    </dl>
    <dl>
        <dt>优秀分数</dt>
        <dd v-for="item in best">{{ item }}</dd>
    </dl>
  </div>
</template>

<script setup>
    import {ref,computed,watch} from 'vue'
    const scoreList = ref([56,43,75,86,94,63])
    const best= computed(()=>{
        return scoreList.value.filter((item)=>item>=80)
    })
    setTimeout(()=>{
        scoreList.value.push(96,65,84)
    },3000)
</script>

<style>

</style>