<script setup lang="ts">
import { ref } from "vue";

const count = ref(1);
const inputValue = ref("Initial value");
</script>

<template>
  <div>
    <h1>Count: {{ count }}</h1>
    <button @click="count++">Increment</button>

    <br />
    <br />

    <p>{{ inputValue }}</p>
    <input type="text" placeholder="Enter text" v-model="inputValue" />
  </div>
</template>

<style scoped></style>
