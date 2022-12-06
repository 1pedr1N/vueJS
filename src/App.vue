<template>
  <NavBar />
  <router-view />
  <FooterApp />
</template>
<script>
import NavBar from "./components/Navbar.vue";
import FooterApp from "./components/FooterApp.vue";
export default {
  name: "App",
  components: {
    NavBar,
    FooterApp,
  },
};
</script>
<style scoped></style>
