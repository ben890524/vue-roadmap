<template>
  <div>{{ route.params.userId }}</div>
</template>
<script setup lang="ts">
import { useRoute } from 'vue-router';

const route = useRoute();
</script>

<script lang="ts">
export default {
  name: 'UserView',
};
</script>

<style scoped lang="scss"></style>
