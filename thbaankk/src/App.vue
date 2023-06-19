<script setup>
import SearchItem from './components/SearchItem.vue'
</script>

<template>
  <div class="container">
    <SearchItem />
  </div>
</template>

<style lang="scss">
body {
  background-color: #f5f5f5;
}
h1 {
  color: green;

  &:hover {
    color: greenyellow;
  }
}
</style>