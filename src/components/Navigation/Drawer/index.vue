<template>
  <div>
    <div class="drawer" :class="{'show': isOpenDrawer, 'change-color': background}">
      <div class="drawer__admin" v-if="isLogin">
        <div class="drawer__admin--photo"></div>
        <div class="drawer__admin--personal">
          <h6 class="drawer__name--admin">Hello, Kate Zimalab</h6>
        </div>
        <div>
          <div>
            <i class="fas fa-user-circle icon__admin"></i>
            <i class="fas fa-tools icon__admin"></i>
            <i class="fas fa-sign-out-alt icon__admin"></i>
          </div>
        </div>
      </div>
      <div class="drawer-navbar">
        <ul class="drawer_navbar--links">
          <li class="drawer_navbar--item">Home</li>
          <li class="drawer_navbar--item">Trend</li>
          <li class="drawer_navbar--item">Workshop</li>
          <li class="drawer_navbar--item">SideLayout</li>
          <li class="drawer_navbar--item">Job</li>
          <li class="drawer_navbar--item">Salary</li>
          <li class="drawer_navbar--item">Shimpo</li>
          <li class="drawer_navbar--item">Javascript</li>
          <li class="drawer_navbar--item">Typescript</li>
        </ul>
      </div>
      <i class="fas fa-times drawer__icon_close--drawer" @click="showNav"></i>
      <div
        class="drawer__logout--button"
        :class="{'change-color': background}"
        @click="isLogin = !isLogin"
      >
        <i class="fas fa-sign-out-alt"></i>
      </div>
    </div>
    <div class="drawer__background" :class="{'layout': isOpenDrawer}" @click="showNav"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isLogin: false
    };
  },
  props: {
    isOpenDrawer: {
      type: Boolean,
      require: true
    },
    background: {
      type: Boolean,
      require: true
    },
    isLogin: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    showNav() {
      setTimeout(() => {
        this.$emit("isCloseDrawer");
      }, 500);
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
  background-color: #17b4cc;
  z-index: 999;
  transition: all 0.5s ease-in-out;

  &.show {
    width: 200px;
    left: 0;
    box-shadow: 7px 0px 15px 5px rgba(17, 0, 0, 0.221);

    &.change-color {
      background-color: rgb(119, 111, 3);
    }
  }
  .drawer__admin {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100%;
    height: 175px;
    border-bottom: 2px solid silver;

    .drawer__admin--photo {
      display: block;
      border-radius: 50%;
      width: 4.5rem;
      height: 4.5rem;
      border: 2px solid rgb(231, 231, 231);
      background-image: url("https://vignette.wikia.nocookie.net/dark-angel/images/7/7b/ZcuI_fGi6LM.jpg/revision/latest?cb=20180926183411&path-prefix=ru");
      background-size: cover;
    }
    .drawer__admin--personal {
      margin: 7px 0;

      .drawer__name--admin {
        color: white;
        margin-top: 5px;
      }
    }
    .icon__admin {
      color: white;
      font-size: 22px;
      margin: 0px 10px;
      cursor: pointer;
    }
  }
  .drawer_navbar--links {
    list-style: none;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 10px;
    left: 0;
    text-align: left;
    vertical-align: middle;

    .drawer_navbar--item {
      display: flex;
      justify-content: center;
      flex-direction: column;
      cursor: pointer;
      width: 100%;
      height: 2.5rem;
      color: rgb(240, 234, 234);
      font-weight: 500;
      padding-left: 17px;
      border-bottom: 1px solid rgba(240, 234, 234, 0.2);
      transition: all 0.1s ease-in-out;
      vertical-align: middle;
    }
    .drawer_navbar--item:hover {
      background-color: #0192a8;
    }
  }
  .drawer__icon_close--drawer {
    position: absolute;
    right: 10px;
    top: 10px;
    color: rgb(240, 234, 234);
    width: 1rem;
    height: 100%;
    cursor: pointer;
  }
  .drawer__logout--button {
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    width: 5rem;
    height: 2.2rem;
    background-color: rgba(183, 239, 255, 0.3);
    border-radius: 4px;
    vertical-align: bottom;
    position: absolute;
    right: 10px;
    bottom: 1.7rem;
    color: white;
  }
  .drawer__logout--button:hover {
    background-color: #fff;
    color: #5f5902;
    transform: rotate(180deg);
  }
  .change-color {
    background-color: #5f5902;
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
