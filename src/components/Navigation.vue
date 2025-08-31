<script setup>
defineOptions({
  name: 'CustomNavigation',
})
import CustomButton from './CustomButton.vue'
import { ref } from 'vue'

const emit = defineEmits(['toggle-sidebar'])

function toggleSidebar() {
  emit('toggle-sidebar')
}

const showPeriodDropdown = ref(false)

const periodList = ref(['Periode 1', 'Periode 2', 'Periode 3'])
</script>

<template>
  <nav class="flex p-4 items-center w-full justify-between bg-white">
    <i class="fa-solid fa-bars text-2xl" @click="toggleSidebar"></i>
    <div class="flex gap-2">
      <div>
        <CustomButton
          class="flex items-center justify-between"
          :onClick="() => (showPeriodDropdown = !showPeriodDropdown)"
        >
          <span>Pilih Periode</span>
          <i class="fa-solid fa-chevron-down ml-2"></i>
        </CustomButton>
        <div
          :class="{ hidden: !showPeriodDropdown }"
          class="absolute mt-2 min-w-36 bg-white shadow-lg group-hover:block"
        >
          <ul class="flex flex-col gap-2">
            <li v-for="period in periodList" :key="period" class="hover:bg-gray-200 p-2">{{ period }}</li>
          </ul>
        </div>
      </div>
      <CustomButton class="flex items-center justify-between">
        <i class="fa-solid fa-bell"></i>
      </CustomButton>
      <CustomButton class="flex gap-2 items-center justify-between">
        <i class="fa-solid fa-arrow-right-from-bracket"></i>
        <span class="text-[#DD3737]">Logout</span>
      </CustomButton>
    </div>
  </nav>
</template>
