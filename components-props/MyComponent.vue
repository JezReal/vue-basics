<script setup lang="ts">
const props = defineProps<{
  title: string;
  description?: string;
}>();
</script>

<template>
  <div>
    <h3>{{ props.title }}</h3>
    <h5>{{ props.description ?? "Default description" }}</h5>
  </div>
</template>

<style scoped>
div {
  border: 1px solid gray;
  margin: 5px;
}
</style>
