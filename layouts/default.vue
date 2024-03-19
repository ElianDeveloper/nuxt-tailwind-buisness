<template>
  <div style="height: 100vh">
    <NavBar />
    <main class="container mx-auto py-4 h-full">
      <router-view />
    </main>
    <!-- <Footer /> -->
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
import NavBar from "../components/NavBar.vue";

export default {
  components: {
    NavBar,
    Footer,
  },
  name: "default",
};
</script>
