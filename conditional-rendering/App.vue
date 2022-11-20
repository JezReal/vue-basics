<script setup lang="ts">
import { ref } from "vue";

const boolVal = ref(false);
const num = ref(1);
const show = ref(true);
</script>

<template>
  <div>
    <h1>Conditional rendering</h1>

    <h3 v-if="boolVal">Boolean value is true!</h3>
    <h3 v-else>Boolean value is false!</h3>
    <button @click="boolVal = !boolVal">Reverse value</button>

    <h2>{{ num }}</h2>
    <h3 v-if="num > 10">Num is larger than 10</h3>
    <h3 v-else-if="num === 10">Num is equal to 10</h3>
    <h3 v-else>Num is less than 10</h3>
    <button @click="num++">Increment</button>

    <br />
    <br />

    <h3 v-show="show">Show is true</h3>
    <h3 v-if="show">V-if is true</h3>
    <button @click="show = !show">Reverse show</button>
  </div>
</template>

<style scoped></style>
