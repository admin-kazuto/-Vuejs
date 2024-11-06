<template>
    <p>total: {{ count }} </p>
    <button @click="sum">tổng</button>
</template>

<script setup>
import { reactive, ref } from 'vue';




const n = reactive([1, 2, 3, 4, 5, 6, 7]);
let count = ref(0)

const sum = () => {
    count.value = 0
   for(let i = 0; i < n.length; i++){
    console.log(n[i])
        count.value += Number(n[i])
   }
}

</script>