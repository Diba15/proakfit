<script setup>
defineProps({
  color: {
    type: String,
    default: 'bg-transparent hover:bg-gray-200 text-gray-500 border-gray-300 border'
  }
})
</script>

<template>
  <button class="font-bold py-2 px-4 rounded text-sm" :class="[color]">
    <slot />
  </button>
</template>
