<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  breadcrumbs: {
    type: Array,
    required: true
  }
})
import CustomBreadcrumbs from './CustomBreadcrumbs.vue'
</script>

<template>
  <div>
    <div>
      <h1 class="text-3xl font-bold text-title">{{ title }}</h1>
      <CustomBreadcrumbs :items="breadcrumbs" />
    </div>

    <main id="content" class="bg-white rounded-lg p-4 w-full flex flex-col gap-4">
      <slot />
    </main>
  </div>
</template>
