<template>
  <div id="main-container">
    <h1>Make Your Burguer</h1>
  </div>
</template>

<script>
export default {
  name: "BannerApp",
};
</script>

<style scoped>
#main-container {
  background-image: url("/images/burger.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 0 -250px;
  height: 500px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}
#main-container h1 {
  color: #fcba03;
  font-size: 42px;
  margin-left: 50px;
  text-align: center;
}
</style>
