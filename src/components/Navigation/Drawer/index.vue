<template>
  <div>
    <div class="drawer" :class="{'show': isOpenDrawer}">
      <div class="drawer__icon_exit">
        <i class="fas fa-bars drawer__icon_exitss"></i>
      </div>
    </div>
    <div class="drawer__background" :class="{'layout': isOpenDrawer}">
      <div></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isOpenDrawer: {
      type: Boolean,
      require: true
    }
  },
  methods: {
    // showNav() {
    //   if (this.isOpenDrawer) {
    //     setTimeout(() => {
    //       this.isOpenDrawer = false;
    //     }, 500);
    //   }
    // }
  }
};
</script>

<style lang="scss" scoped>
.drawer {
  position: absolute;
  top: 0;
  left: -100%;
  width: 0px;
  height: 100vh;
  background-color: #008093;
  border: solid #fff;
  border-width: 0 1px 0 0;
  z-index: 999;
  transition: all 0.5s ease-in-out;

  &.show {
    width: 200px;
    left: 0;
    box-shadow: 7px 0px rgba(17, 0, 0, 0.221);
  }

  &.drawer__icon_exit {
    position: relative;
    width: 2rem;
    height: 100%;

    &.drawer__icon_exitss {
      position: absolute;
      right: 10px;
      top: 10px;
      cursor: pointer;
    }
  }
}
.drawer__background {
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  transition: all 0.5s ease-in-out;

  &.layout {
    height: 100vh;
    width: 100vw;
    position: absolute;
    z-index: 990;
    background-color: black;
    opacity: 0.2;
  }
}
</style>