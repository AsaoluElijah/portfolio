<template>
  <div>
    <NavBar />
    <div id="app">
      <Nuxt />
    </div>
  </div>
</template>
<script>
import NavBar from "../components/NavBar";
export default {
  components: {
    NavBar: NavBar
  }
};
</script>
<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.0.0/animate.min.css");
@import url("https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500;600;700&display=swap");
#app {
  user-select: none;
  font-family: "Quicksand", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 100px;
}
</style>
