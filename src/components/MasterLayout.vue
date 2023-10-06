<script setup>
import Topbar from '@/components/Navbar/Topbar.vue'
import Sidebar from '@/components/Navbar/Sidebar.vue'
</script>

<template>
  <nav class="bg-white py-3 mx-auto border-b">
    <Topbar />
  </nav>
  <div class="grid grid-cols-8">
    <Sidebar />
    <main class="bg-gray-50 min-h-screen col-span-7 p-6">
      <slot></slot>
    </main>
  </div>
</template>

<style scoped></style>
