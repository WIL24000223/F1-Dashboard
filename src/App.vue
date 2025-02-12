<script setup>
import { RouterLink, RouterView } from 'vue-router'
import SideBar from './components/SideBar.vue'
</script>

<template>
  <div class="flex text-stone-200 bg-f1-900">
    <SideBar />
    <RouterView />
  </div>
</template>

<style scoped>
</style>
