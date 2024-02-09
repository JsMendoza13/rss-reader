<script setup>
import { ref } from "vue";
import { useFeedStore } from "../stores/store.js";
const url = ref("");
const store = useFeedStore();

function handleSubmit() {
  if (!!url.value) {
    store.registerNewSource(url.value);
  }
}
</script>

<template>
  <div class="header">
    <form action="" @submit.prevent="handleSubmit">
      <input type="url" required v-model="url" />
      <button type="submit">Add source</button>
    </form>
  </div>
</template>

<style scoped>
.header {
  background: rgb(49, 49, 49);
  grid-area: header;
  justify-self: stretch;
  display: flex;
  justify-content: center;
  padding: 10px;
}

form {
  width: 100%;
  display: flex;
  justify-content: center;
  gap: 5px;
}

input {
  border: none;
  width: 400px;
  padding: 10px;
}

button {
  border: none;
  background-color: rgb(5, 80, 55);
  color: aliceblue;
  padding: 5px 10px;
  cursor: pointer;
  transition: 0.4s;
}
button:hover {
  background: hsla(160, 100%, 37%, 1);
}
</style>
