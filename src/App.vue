<template>
  <NavBar :logo="logo_src" :alt="app_name" />
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
  data(){
    return{
      logo_src: "/images/logo.png",
      app_name: "Make Your Burguer"
    }
  }
};
</script>
<style scoped></style>
