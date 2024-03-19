<template>
  <div v-if="product">
    <h1>{{ product.name }}</h1>
    <h1>{{ product.description }}</h1>
    <h1>{{ product.amount }}</h1>
    <h1>{{ product.price }}</h1>
  </div>
  <h1 v-if="!product">Not found product</h1>
</template>

<script setup>
import { useRouter, useRoute } from "vue-router";
import { useRuntimeConfig } from "#app";

const runtimeConfig = useRuntimeConfig();
const router = useRouter();
const route = useRoute();

const product = ref({
  name: "",
  description: "",
  amount: 0,
  price: 0,
});

const getProductById = async () => {
  try {
    const productId = route.params.id;
    product.value = await $fetch(
      `${runtimeConfig.public.baseUrl}/product/${productId}`
    );

    console.log(product.value);
    // router.push("/products");
  } catch (error) {
    console.log(error);
  }
};

getProductById();
</script>
