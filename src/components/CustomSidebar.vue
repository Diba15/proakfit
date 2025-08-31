<script setup>
import Icon from '../assets/image/icon_proakfit.png'

defineProps({
  toggleSidebar: {
    type: Boolean,
    default: false,
  },
})

const routeList = [
  { name: 'Dashboard', path: '/dashboard' },

]
</script>

<template>
  <aside
    :class="{ 'w-0': !toggleSidebar, 'w-80': toggleSidebar }"
    class="bg-white gap-6 h-full overflow-hidden flex flex-col justify-between pt-4 transition-all duration-500"
  >
    <div class="flex items-center gap-4 justify-between px-4">
      <img :src="Icon" class="max-h-36 max-w-36" alt="" />
    </div>
    <div id="profile" class="flex flex-col items-center">
      <div class="w-32 h-32 bg-gray-300 rounded-full"></div>
      <h2 class="font-bold text-sm mt-2 text-gray-600">User Name</h2>
    </div>
    <div id="menu" class="flex flex-col gap-2">
      <RouterLink
        v-for="route in routeList"
        :key="route.name"
        :to="route.path"
        class="hover:bg-main py-3 px-8 text-gray-600 hover:text-white"
        >{{ route.name }}</RouterLink
      >
    </div>
    <div
      id="manual"
      class="mt-auto p-4 text-sm text-gray-500 w-full cursor-pointer hover:bg-gray-200"
    >
      Manual Pengguna
    </div>
  </aside>
</template>
