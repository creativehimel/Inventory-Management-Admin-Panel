<script setup>
import axios from 'axios'
import { useRoute } from 'vue-router'
import { onBeforeMount, ref } from 'vue'
const product = ref([])
const router = useRoute()
onBeforeMount(() => {
  axios.get(`https://dummyjson.com/products/${router.params.id}`).then((res) => {
    //console.log(res.data.products)
    product.value = res.data
  })
})
</script>

<template>
  <main class="bg-gray-100 min-h-screen">
    <section class="container mx-auto py-10">
      <div class="grid grid-cols-2 bg-white p-8 rounded">
        <div class="flex items-center justify-center">
          <img :src="product.thumbnail" alt="Product image" class="w-[600px]" />
        </div>
        <div class="">
          <div class="space-y-3 pb-2 border-b-2">
            <h3 class="text-4xl font-bold text-gray-600">{{ product.title }}</h3>
            <div class="flex divide-x-2">
              <div class="pr-3">
                <h5 class="text-green-700">Stock Available: {{ product.stock }}</h5>
              </div>
              <div class="pl-3">
                <v-icon name="bi-star-fill" class="text-yellow-500" scale="1" />
                <v-icon name="bi-star-fill" class="text-yellow-500" scale="1" />
                <v-icon name="bi-star-fill" class="text-yellow-500" scale="1" />
                <v-icon name="bi-star-fill" class="text-yellow-500" scale="1" />
                <v-icon name="bi-star-half" class="text-yellow-500" scale="1" />
                <span class="font-inter font-semibold text-gray-600">({{ product.rating }})</span>
              </div>
            </div>
          </div>

          <div class="border-b-2">
            <h3 class="text-lg font-semibold py-2">
              Price:
              <span class="text-green-800 pl-1">
                ৳{{
                  parseFloat(
                    product.price - (product.price * product.discountPercentage) / 100
                  ).toFixed(2)
                }}
              </span>
              <span>
                <span class="text-red-600 pl-4"
                  ><del>৳{{ product.price }}</del></span
                >
              </span>
            </h3>
          </div>
          <div class="space-y-0.5 border-b-2 py-2">
            <h5><span class="text-lg font-semibold">Brand Name:</span> {{ product.brand }}</h5>
            <h5>
              <span class="text-lg font-semibold pr-0.5">Product Category:</span
              >{{ product.category }}
            </h5>
          </div>
          <div class="space-y-0.5 border-b-2 py-2">
            <h5 class="text-lg font-semibold">Description:</h5>
            <p>{{ product.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped></style>
