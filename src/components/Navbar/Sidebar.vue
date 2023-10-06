<script setup>
import NavItem from '@/components/Navbar/NavItem.vue'
</script>

<template>
  <aside class="col-span-1 bg-white border-r">
    <div class="flex flex-col justify-center">
      <div class="bg-slate-100 py-3 rounded my-4 mx-1">
        <div class="flex items-center justify-center">
          <div>
            <img class="w-9 h-9 rounded-full" src="@/assets/images/user.jpg" />
          </div>
          <div class="ps-1.5 font-inter">
            <h5 class="text-md font-semibold">Richard Toland</h5>
            <h6 class="text-xs">Super Admin</h6>
          </div>
        </div>
      </div>
      <div class="w-full">
        <ul class="flex flex-col px-1">
          <NavItem />
        </ul>
      </div>
    </div>
  </aside>
</template>

<style scoped></style>
