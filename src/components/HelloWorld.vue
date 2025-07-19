<script setup lang="ts" vapor>
defineProps<{
  msg: string;
}>();

const handleClick = () => {
  console.log("click");
};

defineExpose({
  handleClick,
});
</script>

<template>
  <h1 @click="handleClick">{{ msg }}</h1>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
