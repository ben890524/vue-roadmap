<template>
  <div>
    <h2>F12請打開後重新整理</h2>
    <button class="px-2.5 my-2.5 py-1 rounded border" @click="addCount">Click to add counter</button>
  </div>
</template>
<script setup lang="ts">
import { ref, watchEffect } from 'vue';

const counter = ref(0);

const addCount = () => {
  counter.value += 1;
};
watchEffect(() => {
  console.log('(watchEffect) The counter is: ', counter.value);
});
</script>

<script lang="ts">
export default {
  name: '',
};
</script>

<style scoped lang="scss"></style>
