<template>
  <div>
    <div>This is reactiveCount: {{ reactiveCount }}</div>
    <div>This is reactiveCount.count: {{ reactiveCount.count }}</div>
    <button class="px-2.5 my-2.5 py-1 rounded border" @click="reactiveCount.count += 1">Add count</button>
  </div>
</template>
<script setup lang="ts">
import { reactive } from 'vue';

const reactiveCount = reactive({
  count: 0,
});
</script>

<script lang="ts">
export default {
  name: '',
};
</script>

<style scoped lang="scss"></style>
