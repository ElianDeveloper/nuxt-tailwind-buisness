<template>
  <!-- Modal toggle -->
  <button
    class="block text-white bg-gray-700 hover:bg-gray-800 focus:ring-4 focus:outline-none focus:ring-gray-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-gray-600 dark:hover:bg-gray-700 dark:focus:ring-gray-800"
    type="button"
    @click="toggleModal = !toggleModal"
  >
    Add Product
  </button>

  <!-- Main modal -->
  <div
    v-if="toggleModal"
    class="overflow-y-auto overflow-x-hidden fixed inset-0 z-50 flex justify-center items-center w-full md:inset-0 h-[calc(100%-1rem)] max-h-full"
  >
    <div class="relative p-4 w-full max-w-md max-h-full">
      <!-- Modal content -->
      <div class="relative bg-white rounded-lg shadow dark:bg-gray-700">
        <!-- Modal header -->
        <div
          class="flex items-center justify-between p-4 md:p-5 border-b rounded-t dark:border-gray-600"
        >
          <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
            Create New Product
          </h3>
          <button
            type="button"
            class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm w-8 h-8 ms-auto inline-flex justify-center items-center dark:hover:bg-gray-600 dark:hover:text-white"
            @click="toggleModal = false"
          >
            <svg
              class="w-3 h-3"
              aria-hidden="true"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 14 14"
            >
              <path
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6"
              />
            </svg>
            <span class="sr-only">Close modal</span>
          </button>
        </div>
        <!-- Modal body -->
        <form class="p-4 md:p-5" @submit.prevent="submitProduct">
          <div class="grid gap-4 mb-4 grid-cols-2">
            <div class="col-span-2">
              <label
                for="name"
                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
                >Name</label
              >
              <input
                type="text"
                name="name"
                id="name"
                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-600 dark:border-gray-500 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                placeholder="Type product name"
                v-model="newProduct.name"
                required
              />
            </div>
            <div class="col-span-2 sm:col-span-1">
              <label
                for="price"
                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
                >Price</label
              >
              <input
                type="number"
                name="price"
                id="price"
                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-600 dark:border-gray-500 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                placeholder="$2999"
                v-model="newProduct.price"
                required
              />
            </div>
            <div class="col-span-2 sm:col-span-1">
              <label
                for="price"
                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
                >Amount</label
              >
              <input
                type="number"
                name="price"
                id="price"
                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-600 dark:border-gray-500 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                placeholder="Amount"
                v-model="newProduct.amount"
                required
              />
            </div>
            <!-- <div class="col-span-2 sm:col-span-1">
              <label
                for="category"
                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
                >Category</label
              >
              <select
                id="category"
                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-600 dark:border-gray-500 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
              >
                <option selected="true">Select category</option>
                <option value="Food">Food</option>
                <option value="Drink">Drink</option>
              </select>
            </div> -->
            <div class="col-span-2">
              <label
                for="description"
                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
                >Product Description</label
              >
              <textarea
                id="description"
                rows="4"
                class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-600 dark:border-gray-500 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                placeholder="Write product description here"
                v-model="newProduct.description"
                required
              ></textarea>
            </div>
          </div>
          <button
            type="submit"
            class="text-white inline-flex items-center bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
          >
            <svg
              class="me-1 -ms-1 w-5 h-5"
              fill="currentColor"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z"
                clip-rule="evenodd"
              ></path>
            </svg>
            Add new product
          </button>
        </form>
      </div>
    </div>
  </div>
  <div
    v-if="toggleModal"
    class="absolute inset-0 z-40 bg-black opacity-25"
  ></div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";
import { useRuntimeConfig } from "#app";

const runtimeConfig = useRuntimeConfig();
const router = useRouter();
const toggleModal = ref(false);

const newProduct = reactive({
  name: "",
  description: "",
  amount: null,
  price: null,
});

const submitProduct = async () => {
  try {
    const response = await $fetch(`${runtimeConfig.public.baseUrl}/product`, {
      method: "POST",
      body: JSON.stringify(newProduct),
    });

    if (response.error) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }

    console.log("Product added successfully");

    router.push("/products");

    toggleModal.value = false;
  } catch (error) {
    console.log("Error add product --> " + error);
  }
};
</script>
