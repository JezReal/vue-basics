<script setup lang="ts">
import { computed, reactive, ref } from "vue";

const name = ref("Jezreel");

const coolObject = reactive({
  id: 1,
  language: "Typescript",
});

const primitive = reactive(1);

const coolObjectRef = ref({
  id: 1,
  language: "Kotlin",
});

const author = ref({
  name: "Martin, Jezreel",
  books: ["book 1", "book 2", "book 3"],
});

const hasPublishedBooks = computed(() => {
  if (author.value.books.length > 0) {
    return "Yes";
  }

  return "No";
});

const inputValue = ref("");
const errorMessage = computed(() => {
  if (inputValue.value.length < 5) {
    return "Must be at least 5 characters";
  }

  return "";
});

function updateInputValue($event) {
  inputValue.value = $event.target.value;
}

function changeName() {
  name.value = "Joshua";
}

function resetName() {
  name.value = "Jezreel";
}

function updateCoolObject() {
  coolObject.language = "Javascript";
}

function updateCoolObjectRef() {
  coolObjectRef.value.language = "C#";
}
</script>

<template>
  <div>
    <h1>Name: {{ name }}</h1>

    <button @click="changeName">Change name</button>
    <button @click="resetName">reset name</button>

    <h3>{{ coolObject.language }}</h3>
    <h3>{{ coolObjectRef.language }}</h3>

    <button @click="updateCoolObject">Update cool object</button>
    <button @click="updateCoolObjectRef">Update cool object ref</button>

    <h4>Non reactive count: {{ primitive }}</h4>
    <button @click="primitive++">INc</button>

    <h3>{{ author.name }}</h3>
    <h4>Has published books: {{ hasPublishedBooks }}</h4>

    <input
      type="text"
      placeholder="Enter some text"
      @input="updateInputValue"
    />
    <p>{{ errorMessage }}</p>
  </div>
</template>

<style scoped></style>
