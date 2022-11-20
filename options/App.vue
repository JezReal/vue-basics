<script setup lang="ts">
import { ref } from "vue";

// export default {
//   data() {
//     return {
//       count: 1,
//     };
//   },

//   methods: {
//     increment() {
//       this.count++;
//     },
//   },
// };

const count = ref(1);

function increment() {
  count.value++;
}
</script>

<template>
  <div>
    <h3>Count: {{ count }}</h3>
    <button @click="increment">Increment</button>
  </div>
</template>

<style scoped></style>
