<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>

    <div class="p-4">
      <nav class="flex gap-3">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/dashboard">Dashboard</RouterLink>
      </nav>
    </div>
  </header>

  <div class="p-4">
    <RouterView />
  </div>
</template>

<style scoped>
</style>
