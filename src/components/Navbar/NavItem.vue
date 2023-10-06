<script setup>
import { RouterLink } from 'vue-router'
const navItems = [
  {
    id: 1,
    name: 'Dashboard',
    icon: '<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-pie-chart"><path d="M21.21 15.89A10 10 0 1 1 8 2.83"></path><path d="M22 12A10 10 0 0 0 12 2v10z"></path></svg>',
    link: '/'
  },
  {
    id: 2,
    name: 'Products',
    icon: '<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-shopping-bag"><path d="M6 2L3 6v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V6l-3-4z"></path><line x1="3" y1="6" x2="21" y2="6"></line><path d="M16 10a4 4 0 0 1-8 0"></path></svg>',
    link: '/products'
  },
  {
    id: 3,
    name: 'Orders',
    icon: '<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-shopping-cart"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>',
    link: '/orders'
  },
  {
    id: 1,
    name: 'Customers',
    icon: '<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-users"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>',
    link: '/customers'
  }
]
</script>

<template>
  <li v-for="navItem in navItems" :key="navItem.id">
    <RouterLink
      :to="navItem.link"
      class="active:text-green-900 text-gray-500 hover:text-[#4eb529] font-inter font-semibold active:bg-green-100 py-2 px-6 flex items-center gap-x-1.5 text-md rounded"
    >
      <span v-html="navItem.icon"></span>
      {{ navItem.name }}
    </RouterLink>
  </li>
</template>

<style scoped>
.router-link-active,
.router-link-exact-active {
  background-color: #dcf0d4;
  color: #4eb529;
}
</style>
