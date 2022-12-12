<!-- eslint-disable prettier/prettier -->
<template>
     <div>
     <router-link to="/"> <img :src="logo" :alt="alt"/> </router-link>   
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
     </div>
</template>
<script>
export default {
  name: "NavBar",
  props: ["logo", "alt"],
};
</script>
