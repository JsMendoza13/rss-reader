<script setup>
import { useFeedStore } from "../stores/store.js";

const store = useFeedStore();

function handleClick(source) {
  store.loadSource(source);
}
</script>

<template>
  <div class="sidebar">
    <div v-for="(source, index) in store.sources" :key="index">
      <a href="#" @click.prevent="() => handleClick(source)">{{
        source.name
      }}</a>
    </div>
  </div>
</template>

<style scoped>
.sidebar {
  grid-column-start: 1;
  grid-column-end: 2;
  background-color: #222121;
}
</style>
