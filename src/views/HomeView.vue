<template>
  <BannerApp />
  <div class="main-container">
    <h1>Monte o seu burguer:</h1>
    <FormApp />
  </div>
</template>
<script>
import BannerApp from "../components/Banner.vue";
import FormApp from "../components/FormApp.vue";
export default {
  name: "HomeView",
  components: {
    BannerApp,
    FormApp,
  },
};
</script>
