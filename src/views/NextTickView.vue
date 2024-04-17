<script setup lang="ts">
import { ref, nextTick } from 'vue';

const count = ref(0);

async function increment() {
  count.value++;

  // DOM not yet updated
  console.log(document.getElementById('counter')?.textContent); // 0
  count.value++;

// DOM not yet updated
  console.log(document.getElementById('counter')?.textContent); // 0

// DOM not yet updated
  count.value++;
  console.log(document.getElementById('counter')?.textContent); // 0

  await nextTick();
  // DOM is now updated
  console.log(document.getElementById('counter')?.textContent); // (x+3)
}
</script>

<template>
  <button class="px-2.5 my-2.5 py-1 rounded border" id="counter" @click="increment">
    Click to add counter. {{ count }}
  </button>
</template>
