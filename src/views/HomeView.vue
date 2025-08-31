<script setup>
import TemplateView from '@/components/TemplateView.vue';
</script>

<template>
  <TemplateView
      title="Dashboard"
      :breadcrumbs="[{ text: 'Home', to: '/' }, { text: 'Dashboard' }]"
    >
      <template #default>
        <h2 class="text-2xl font-semibold text-title">Data Mahasiswa</h2>
        <div class="h-0.5 bg-gray-600 w-full"></div>
        <p class="text-gray-600">This is your dashboard where you can manage your activities.</p>
      </template>
    </TemplateView>
</template>
