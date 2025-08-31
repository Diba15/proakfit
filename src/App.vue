<script setup>
import {ref} from 'vue'
import { RouterView } from 'vue-router'
import CustomNavigation from './components/Navigation.vue'
import CustomSidebar from './components/CustomSidebar.vue'

const toggleSidebar = ref(true)

if (localStorage.getItem('sidebar') === null) {
  localStorage.setItem('sidebar', JSON.stringify(toggleSidebar.value))
} else {
  toggleSidebar.value = JSON.parse(localStorage.getItem('sidebar'))
}


function toggleSidebarFunction() {
  toggleSidebar.value = !toggleSidebar.value
  localStorage.setItem('sidebar', JSON.stringify(toggleSidebar.value))
}
</script>

<template>
  <header>

  </header>

  <div class="flex h-screen">
    <CustomSidebar :toggleSidebar="toggleSidebar" />
    <div class="w-screen flex flex-col gap-1">
      <CustomNavigation @toggle-sidebar="toggleSidebarFunction" />
      <RouterView class="px-8 pt-4 w-full" />
    </div>
  </div>
</template>

<style scoped>
</style>
