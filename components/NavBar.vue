<template>
  <nav
    class="flex items-center justify-between h-16 bg-gray-800 text-white px-4 md:px-8"
  >
    <nuxt-link class="text-xl font-bold">Business App</nuxt-link>

    <ul class="hidden md:flex space-x-6">
      <li>
        <nuxt-link
          class="hover:cursor-pointer"
          v-bind:style="{ color: 'inherit' }"
        >
          Home
        </nuxt-link>
      </li>
      <li>
        <button @click="toggleMenu">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"
            />
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"
            />
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"
            />
          </svg>
        </button>
      </li>
    </ul>
  </nav>

  <div
    v-show="showMenu"
    class="fixed inset-0 bg-gray-800 opacity-75 backdrop-blur transition duration-300 ease-in-out z-50"
  >
    <ul
      class="absolute top-0 left-0 w-full h-full flex flex-col items-center justify-center space-y-4 text-center text-xl font-bold text-white"
    >
      <li @click="toggleMenu">
        <nuxt-link to="/">Products</nuxt-link>
      </li>
      <li @click="toggleMenu">
        <nuxt-link to="/">Sells</nuxt-link>
      </li>
      <li @click="toggleMenu">
        <nuxt-link to="/">Expenses</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
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
