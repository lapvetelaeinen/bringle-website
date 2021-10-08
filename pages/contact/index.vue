<template>
  <div class="wrapper">
    <!-- Mobile nav -->
    <MobileNav id="mobile-nav" />
    <!-- Navigation -->
    <section class="main-nav">
      <nuxt-link to="/" class="logo"><h1>Bringle</h1></nuxt-link>
      <ul>
        <li>
          <nuxt-link to="/about" class="nav-link">Om</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/contact" class="nav-link">Kontakt</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/order" class="nav-link">Beställ</nuxt-link>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#mobile-nav {
  display: none;
}

.main-nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: absolute;
  width: 100%;
  z-index: 99;
  padding: 15px 50px;
  background: rgb(0, 53, 88);

  ul {
    display: flex;
    list-style: none;
  }
  .nav-link {
    @include primary-regular;
    color: #ddd;
    text-decoration: none;
    font-size: 25px;
    margin-left: 100px;
  }
  .logo {
    text-decoration: none;
  }
  h1 {
    @include primary-bold;
    color: #ddd;
    font-size: 35px;
  }
  a:hover {
    color: #118ab2;
  }
}

@media only screen and(max-width: 768px) {
  .main-nav {
    display: none;
  }

  #mobile-nav {
    display: block;
  }
}
</style>
