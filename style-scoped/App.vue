<script setup lang="ts">
import MyComponent from "./MyComponent.vue";
</script>

<template>
  <div>
    <h1>Style scoped</h1>
    <my-component />
  </div>
</template>

<style scoped>
h1 {
  font-size: 150px;
}
</style>
