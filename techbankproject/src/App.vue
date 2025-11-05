<template>
  <div id="app">
    <Navbar />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import AppNavbar from "@/components/Navbar.vue";
import AppFooter from "@/components/Footer.vue";

export default {
  name: "App",
  components: {
    Navbar: AppNavbar,
    Footer: AppFooter,
  },
};
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

body {
  margin: 0;
  padding: 0;
}
</style>
