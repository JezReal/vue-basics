<script setup lang="ts">
import { ref } from "vue";

const names = ref([
  {
    id: 1,
    name: "Jezreel",
  },
  {
    id: 2,
    name: "Joshua",
  },
  {
    id: 3,
    name: "Martin",
  },
]);
</script>

<template>
  <div v-for="name in names" :key="name.id">
    <ul>
      <li>{{ name.name }}</li>
    </ul>
  </div>
</template>

<style scoped></style>
