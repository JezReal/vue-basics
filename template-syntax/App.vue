<script setup lang="ts">
import { ref } from "vue";

const message = "Goodbye owrld";
const name = "Jezreel";

function hasReturnValue() {
  return "I have a value";
}

function noReturnValue() {
  console.log("I have no value");
}

const dynamicId = "2";
const dynamicClass = ref("default");

function removeClass() {
  dynamicClass.value = null;
}

function addClass() {
  dynamicClass.value = "default";
}
</script>

<template>
  <div>
    <h3>
      {{ message }}
    </h3>

    <p>{{ name }}</p>
    <p>{{ 1 + 12 }}</p>
    <p>{{ 1 - 12 }}</p>

    <p>{{ hasReturnValue() }}</p>
    <p>{{ noReturnValue() }}</p>

    <h3 v-bind:id="dynamicId">I have a dynamic id</h3>
    <h3 v-bind:class="dynamicClass" class="static-class">
      I have a dynamic id
    </h3>

    <button @click="removeClass">Remove class</button>
    <button @click="addClass">add class</button>
  </div>
</template>

<style scoped></style>
