<template>
  <div id="app">
    <div id="nav">
      <Navbar />
      <router-link to="/"></router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
import Navbar from "./components/Navigation";
export default {
  components: {
    Navbar
  }
};
</script>
<style>
#app {
  margin: 0;
  padding: 0;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
