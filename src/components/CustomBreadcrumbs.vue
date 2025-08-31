<script setup>
defineProps({
  lists: {
    type: Array,
    required: true,
    default: () => [
      { name: 'Home', path: '/' },
      { name: 'Dashboard', path: '/dashboard' }
    ],
  }
})
</script>

<template>
  <nav class="text-sm text-gray-500 mb-4" aria-label="Breadcrumb">
    <ol class="list-none p-0 inline-flex">
      <li v-for="(item, index) in lists" :key="index" class="flex items-center">
        <RouterLink
          v-if="index !== lists.length - 1"
          :to="item.path"
          class="text-gray-500 hover:text-gray-700"
        >
          {{ item.name }}
        </RouterLink>
        <span v-else class="text-gray-700 font-semibold">{{ item.name }}</span>
        <span v-if="index !== lists.length - 1" class="mx-2">/</span>
      </li>
    </ol>
  </nav>
</template>
