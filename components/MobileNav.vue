<template>
  <div class="container">
    <div class="menu" v-show="showMenu">
      <div class="close" @click="toggleMenu">X</div>
      <ul>
        <li>
          <nuxt-link to="/">Hem</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/contact">Kontakta oss</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/order">Beställ</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/about">Om oss</nuxt-link>
        </li>
      </ul>
    </div>
    <div class="nav-bar">
      <i class="fas fa-bars" @click="toggleMenu" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showMenu: false,
    };
  },
  created() {
    window.addEventListener("click", this.close);
  },

  beforeDestroy() {
    window.removeEventListener("click", this.close);
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    },
    close(e) {
      if (!this.$el.contains(e.target)) {
        this.showMenu = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  position: relative;
}
.nav-bar {
  position: fixed;
  top: 0;
  z-index: 1;
  background: rgb(0, 53, 88);
  width: 100%;
}
i {
  padding-block: 15px;
  padding-left: 20px;
  font-size: 30px;
  color: #ddd;
  cursor: pointer;
}

.menu {
  display: block;
  position: fixed;
  z-index: 2;
  background: rgb(32, 78, 138);
  height: 100vh;

  ul {
    padding: 10px 30px;
    list-style: none;
    margin-top: 60px;
  }

  li {
    @include primary-regular;
    font-size: 22px;
    color: #ddd;
    margin-bottom: 30px;
    cursor: pointer;

    a {
      text-decoration: none;
      color: #ddd;
    }
  }

  .close {
    position: fixed;
    left: 150px;
    top: 10px;
    padding: 5px 10px;
    @include primary-bold;
    font-size: 27px;
    color: #ddd;
    background-color: rgb(29, 68, 128);
    border-radius: 10px;
    cursor: pointer;
  }
}
</style>
