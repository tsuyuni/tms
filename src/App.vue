<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Test from "./components/Test.vue"

const number = 3;
</script>

<template>
  <RouterView />
</template>

<style scoped>
section {
  border: 1px solid yellow;
}
</style>
