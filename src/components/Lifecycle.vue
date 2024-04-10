<template>
  <div>
    <h1>Lifecycle Counter: {{ counter }}</h1>
    <button @click="counter += 1">Add <- Click to add counter</button>
  </div>
</template>
<script setup lang="ts">
import { onBeforeMount, onMounted, onBeforeUnmount, onUnmounted, ref, onBeforeUpdate, onUpdated } from 'vue';

const counter = ref<number>(0);

onBeforeMount(() => {
  console.log('In onBeforeMount');
});

onMounted(() => {
  console.log('In onMounted');
});

onBeforeUpdate(() => {
  console.log('In onBeforeUpdate');
});
onUpdated(() => {
  console.log(`In onUpdated and counter is ${counter.value}`);
});

onBeforeUnmount(() => {
  console.log('In onBeforeUnmount');
});

onUnmounted(() => {
  console.log('In onUnmounted');
});
</script>

<script lang="ts">
export default {
  name: '',
};
</script>

<style scoped lang="scss"></style>
