<script setup lang="tsx" vapor>
import { onMounted, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
const data = ref([{ name: "Item 1" }, { name: "Item 2" }, { name: "Item 3" }]);
const helloWorld = ref<InstanceType<typeof HelloWorld>>();

onMounted(() => {
  console.log(helloWorld.value, 111);
});

const Comp = ({ data }: { data: any }) => {
  const styles = defineStyle.css(`
    .foo {
      color: blue;
    }
  `);
  return (
    <div class={styles.foo} v-for={item in data}>
      {item.name}
    </div>
  );
};

const inputValue = ref("");

const InputComp = () => {
  const modelValue = defineModel<string>();
  const handleChange = (e: Event) => {
    console.log(inputValue.value, (e.target as HTMLInputElement).value);
  };
  return (
    <input onChange={handleChange} v-model={modelValue.value} type="text" />
  );
};
</script>

<template>
  <div>
    <Comp :data="data" />
    <HelloWorld ref="helloWorld" msg="Vite + Vue" />
    <InputComp v-model="inputValue" />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
