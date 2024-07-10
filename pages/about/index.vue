<script setup lang="ts">
import A from '@/components/A'
import {useAsyncData} from "#app";

const { data } = await useFetch('/api/hello')
const {a} = await useAsyncData("",()=>{

})

async function divClick(){
  const { data } = await useFetch('/api/hello')
  console.log(data)
}
</script>

<template>
  <pre>
    <div @click="divClick">about页面</div>
    <div>{{ data }}</div>
  </pre>
</template>