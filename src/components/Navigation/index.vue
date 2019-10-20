<template>
  <div>
    <b-navbar type="dark" class="navbar_main" :class="{'background-navbar': background}">
      <div class="navbar--navigation">
        <div>
          <i class="fas fa-bars navbar--burger" @click="isOpenDrawer = !isOpenDrawer"></i>
          <b-navbar-brand href="#">NavBar</b-navbar-brand>
        </div>
        <div class="mode__color" @click="changeMode" :class="{'change-background': background}">
          <div>
            <i class="fas fa-sun change__mode-color"></i>
          </div>
        </div>
      </div>
    </b-navbar>
    <div class="navbar__hamb_container">
      <Drawer
        :background="background"
        :isOpenDrawer="isOpenDrawer"
        @isCloseDrawer="isOpenDrawer = !isOpenDrawer"
        :isLogin="isLogin"
      />
    </div>
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
  props: {
    background: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    changeMode() {
      this.$emit("background");
    }
  },
  components: {
    Drawer
  }
};
</script>

<style lang="scss" scoped>
.navbar_main {
  background-color: #03aaaa;
}
.background-navbar {
  background-color: rgb(95, 89, 2);
}
.navbar--navigation {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.navbar--burger {
  width: 2rem;
  height: 100%;
  margin: 0 1rem 0 0;
  color: white;
  cursor: pointer;
}
.navbar__hamb_container {
  position: relative;
}

.mode__color {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 1.8rem;
  height: 1.8rem;
  background-color: rgb(11, 214, 207);
  border-radius: 50%;
  cursor: pointer;
  text-align: center;

  .change__mode-color {
    width: 15px;
    height: 100%;
    color: white;
  }
}
.change-background {
  background-color: rgb(39, 44, 2);
}
</style>