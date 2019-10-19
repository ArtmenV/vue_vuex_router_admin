<template>
  <div>
    <div class="drawer" :class="{'show': isOpenDrawer}">
      <div class="drawer-navbar">
        <ul class="drawer_navbar--links">
          <li class="drawer_navbar--item">Home</li>
          <li class="drawer_navbar--item">Trend</li>
          <li class="drawer_navbar--item">Worshop</li>
          <li class="drawer_navbar--item">SideLayout</li>
          <li class="drawer_navbar--item">Job</li>
          <li class="drawer_navbar--item">Salary</li>
          <li class="drawer_navbar--item">Shimpo</li>
          <li class="drawer_navbar--item">Javascript</li>
          <li class="drawer_navbar--item">Typescript</li>
        </ul>
      </div>
      <div class="drawer__icon">
        <i class="fas fa-bars drawer__icon_exitss" @click="showNav"></i>
      </div>
    </div>
    <div class="drawer__background" :class="{'layout': isOpenDrawer}" @click="showNav">
      <div></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    ourCompany: [{}];
  },
  props: {
    isOpenDrawer: {
      type: Boolean,
      require: true
    }
  },
  methods: {
    showNav() {
      // this.isOpenDrawer = false;
      setTimeout(() => {
        this.$emit("isCloseDrawer");
      }, 300);
    }
  }
};
</script>

<style lang="scss" scoped>
.drawer {
  position: fixed;
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
}
.drawer__icon {
  .drawer__icon_exitss {
    position: absolute;
    right: 10px;
    top: 10px;
    color: rgb(240, 234, 234);
    width: 1rem;
    height: 100%;
    cursor: pointer;
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
.drawer_navbar--links {
  list-style: none;
  display: flex;
  flex-direction: column;
  margin-top: 15px;
  left: 0;
  padding: 7;
  text-align: left;
}
.drawer_navbar--item {
  cursor: pointer;
  width: 100%;
  height: 3rem;
  color: rgb(240, 234, 234);
  font-weight: 700;
  padding-left: 10px;
  border-bottom: 1px solid rgba(240, 234, 234, 0.2);
}
</style>