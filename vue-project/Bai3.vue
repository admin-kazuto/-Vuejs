<template>

  <div>
    <h1>{{ greeting }}</h1>
  </div>

  <button :title="buttonTitle" @click="changGreeting">Click để thay đổi</button>

</template>

<script setup>
import { ref } from "vue";

const greeting = ref("xin chào bạn")
const buttonTitle = ref("nhấn để thay đổi lời chào")

const changGreeting = () => {
  greeting.value = "hello world"
  buttonTitle.value = "lời chào đã được cập nhật"
}
</script>