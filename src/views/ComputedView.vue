<template>
  <div>
    <p>我今年 {{ age }} 歲</p>
    <button class="px-2.5 my-2.5 py-1 rounded border" @click="age += 1">Click to add age</button>
    <p>我明年預計 {{ nextYearAge }} 歲</p>
  </div>
</template>
<script setup lang="ts">
import { computed, ref } from 'vue';

const age = ref(1);

const nextYearAge = computed(() => age.value + 1);
</script>

<script lang="ts">
export default {
  name: '',
};
</script>

<style scoped lang="scss"></style>
