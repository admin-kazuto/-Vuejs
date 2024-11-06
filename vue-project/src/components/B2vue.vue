<template>
    <div>
      person : {{ status }}
      <button @click="add">click</button>
    </div>
  </template>
  <script setup>
  import { reactive } from 'vue';
  
  const status = reactive({
    name : "kuro",
    age : 30,
    city : "Hà Nội"
  })
  
  const add = () => {
    status.age++
  }
  
  </script>
  
  