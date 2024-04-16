<template>
  <div>
    <h2>F12請打開後重新整理</h2>
    <button class="px-2.5 my-2.5 py-1 rounded border" @click="addCount">Click to add counter</button>
  </div>
</template>
<script setup lang="ts">
import { reactive, ref, watch } from 'vue';

const counter = ref(0);
const watchSetTest = ref(999999);

const counterReactive = reactive({ state: 0 });
const counterRecursiveReactive = reactive({ recursive: { state: 0 } });

const addCount = () => {
  counter.value += 1;
  counterReactive.state += 1;
  counterRecursiveReactive.recursive.state += 1;
};

watch(counter, () => {
  console.log(`(base watcher) The counter value is: ${counter.value}`);
});

watch(counter, (value, oldValue) => {
  console.log(`((new/old) watcher) The counter value is: ${value}/${oldValue}`);
});

watch([counter, watchSetTest], (value, oldValue) => {
  console.log(`(source[] watcher) The counter value is: ${JSON.stringify(value)}/${JSON.stringify(oldValue)}`);
});

watch(counterReactive, () => {
  console.log(`(reactive default to deep watcher) The counter value is: ${counterReactive.state}`);
});

watch(
  () => counterReactive.state,
  () => {
    console.log(`(getter watcher) The counter value is: ${counterReactive.state}`);
  }
);

watch(
  counterRecursiveReactive,
  () => {
    console.log(`(deeper watcher) The counter value is: ${counterRecursiveReactive.recursive.state}`);
  },
  { deep: true }
);

watch(
  counter,
  () => {
    console.log(`(immediate watcher) The counter value is: ${counter.value}`);
  },
  {
    immediate: true,
  }
);
</script>

<script lang="ts">
export default {
  name: '',
};
</script>

<style scoped lang="scss"></style>
