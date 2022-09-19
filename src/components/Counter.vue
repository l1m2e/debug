<script setup lang="ts">
import { Dialog } from '@varlet/ui'
import '@varlet/ui/es/dialog/style/index'
const test = ref({name:'test'})
const change = ()=>{ test.value = {name:'retset'}}
watch(test,(v)=>{
  console.log('watch',v);
  //注释掉下面 不会触发bug
  Dialog({
  title: '警告',
  message: '是否要结束签到'
 })
})
</script>

<template>
  <div btn @click="change">change</div>
</template>
