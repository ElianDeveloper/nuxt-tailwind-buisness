<template>
  <div class="flex justify-end">
    <AddProducts />
  </div>
  <CardProduct :products="products" />

  <h1 v-if="products.length === 0">No products found</h1>
</template>

<script setup>
import { ref, onMounted } from "vue";

const products = ref([]);

onMounted(async () => {
  try {
    const response = await fetch("http://localhost:3001/api/products");

    if (!response.ok) {
      throw new Error("Failed to fetch products");
    }

    products.value = await response.json();
  } catch (error) {
    console.log(error);
  }
});
</script>
