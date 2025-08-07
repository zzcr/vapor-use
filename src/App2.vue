<script setup lang="ts" vapor>
import { ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
const message = ref("Vite + Vue");
const handleClick = () => {
  message.value = "Hello World!"; // Update the message when the button is clicked
};
</script>

<template>
  <button @click="handleClick">点击我改变值</button>
  <HelloWorld v-for="item in 30000" :msg="message" />
</template>

<style scoped>
button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: aquamarine;
  cursor: pointer;
}
</style>
