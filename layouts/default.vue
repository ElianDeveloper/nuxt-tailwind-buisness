<template>
  <div style="height: 100vh">
    <Header />
    <main class="container mx-auto py-4 h-full">
      <router-view />
    </main>
    <!-- <Footer /> -->
  </div>
</template>

<!-- <template>
  <div style="height: 100vh; display: flex; flex-direction: column">
    <Header />
    <main class="container mx-auto py-4 h-full">
      <router-view />
    </main>
    <Footer />
  </div>
</template> -->

<script>
import Footer from "../components/Footer.vue";
import Header from "../components/Header.vue";

export default {
  components: {
    Header,
    Footer,
  },
  name: "default",
};
</script>
