<template>
  <div class="app" :class="{'app-background' : background}">
    <div id="nav">
      <Navbar :background="background" @background="background= !background" />
      <router-link to="/"></router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
import Navbar from "./components/Navigation";
export default {
  data() {
    return {
      background: false
    };
  },
  components: {
    Navbar
  }
};
</script>
<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=IBM+Plex+Sans:400,500i,700&display=swap");
body {
  font-family: "IBM Plex Sans", sans-serif;
}
.app {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
.app-background {
  background-color: rgb(39, 44, 2);
  width: 100vw;
  height: 100vh;
  color: white;
}
ul {
  padding-inline-start: 0px;
}
</style>
