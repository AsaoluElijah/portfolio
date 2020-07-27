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
#app {
  margin-top: 100px;
}
</style>
