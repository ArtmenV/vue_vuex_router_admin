<template>
  <div>
    <b-navbar type="dark" variant="info">
      <i class="fas fa-bars navbar--burger" @click="isOpenDrawer = !isOpenDrawer"></i>
      <b-navbar-brand href="#">NavBar</b-navbar-brand>
    </b-navbar>
    <Drawer :isOpenDrawer="isOpenDrawer" />
  </div>
</template>

<script>
import Drawer from "./Drawer";
export default {
  name: "navbar",
  data() {
    return {
      isOpenDrawer: false
    };
  },
  components: {
    Drawer
  }
};
</script>

<style lang="scss" scoped>
.navbar--burger {
  width: 2rem;
  height: 100%;
  margin: 0 1rem 0 0;
  color: white;
  cursor: pointer;
}
</style>