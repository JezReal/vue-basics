<script setup lang="ts">
import MyComponent from "./MyComponent.vue";

const dynamicTitle = "dynamic title";
</script>

<template>
  <div>
    <h1>Components</h1>
    <my-component title="title one" description="description one" />
    <my-component title="title two" description="description two" />
    <my-component :title="dynamicTitle" description="description three" />
    <my-component :title="dynamicTitle" />
  </div>
</template>

<style scoped></style>
