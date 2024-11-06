<template>
    <p>status : {{ status }}</p>
    <button @click="changeStatus">click</button>
</template>

<script setup>
import { ref } from 'vue';

const status = ref("online")

const changeStatus = () => {
    if (status.value === "online") {
        status.value = "offline"
    } else {
        status.value = "online"
    }
}
</script>