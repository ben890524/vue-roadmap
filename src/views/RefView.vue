<template>
  <div>
    <div>This is count: {{ counter }}</div>
    <button class="px-2.5 my-2.5 py-1 rounded border" @click="counter += 1">Add count</button>
    <div>This is ref count: {{ refCounter }}</div>
    <button class="px-2.5 my-2.5 py-1 rounded border" @click="refCounter += 1">Add ref count</button>
  </div>
</template>
<script setup lang="ts">
import { ref } from 'vue';

let counter = 0;

const refCounter = ref(0);
</script>

<script lang="ts">
export default {
  name: '',
};
</script>

<style scoped lang="scss"></style>
