<template>
  <nav
    class="flex items-center justify-between h-16 bg-gray-800 text-white px-4 md:px-8"
  >
    <nuxt-link class="text-xl font-bold">Business App</nuxt-link>

    <ul class="hidden md:flex space-x-6">
      <li>
        <nuxt-link
          to="/"
          class="hover:cursor-pointer"
          v-bind:style="{ color: 'inherit' }"
        >
          Home
        </nuxt-link>
      </li>
      <li>
        <nuxt-link
          to="/products"
          class="hover:cursor-pointer"
          v-bind:style="{ color: 'inherit' }"
          >Products</nuxt-link
        >
      </li>
      <li>
        <nuxt-link
          to="/"
          class="hover:cursor-pointer"
          v-bind:style="{ color: 'inherit' }"
          >Sells</nuxt-link
        >
      </li>
      <li>
        <nuxt-link
          to="/"
          class="hover:cursor-pointer"
          v-bind:style="{ color: 'inherit' }"
          >Expenses</nuxt-link
        >
      </li>
    </ul>
  </nav>
</template>

<script>
import Sidebar from "./Sidebar.vue";

export default {
  data() {
    return {
      showMenu: false,
    };
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    },
  },
};
</script>
