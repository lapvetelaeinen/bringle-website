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
    <!-- Hero -->
    <section class="hero">
      <div class="hero-content">
        <h1 class="heading">Ha stenkoll på dina kärror</h1>
        <div class="btn-container">
          <a href="#" class="btn">Se video</a>
          <nuxt-link to="/contact" class="btn" id="btn-2"
            >Kontakta oss</nuxt-link
          >
        </div>
      </div>
    </section>
    <!-- Intro -->
    <section class="intro-section">
      <div class="img-container">
        <img
          src="~/assets/images/laptopphone.png"
          alt="phone and laptop"
          id="desktop"
        />
        <img
          src="~/assets/images/devices-mobile.png"
          alt="phone and laptop"
          id="mobile"
        />
      </div>
      <div class="text-container">
        <h3>Ordning och reda</h3>
        <p>
          Oklarheter kring antal lämnade och mottagna kärror är ett minne blott
          med Bringle. Genom att registrera leveranser i applikationen så får
          mottagaren ett bekräftelsemeddelande med nödvändig information för att
          säkertställa rätt antal kärror och tillbehör vid leverans och
          upphämtning.
        </p>
      </div>
    </section>
    <!-- Functions -->
    <section class="functions-section">
      <h3>Vi har verktygen som du behöver</h3>
      <div class="functions">
        <FunctionCard
          class="func"
          title="Lagerhantering"
          icon="fas fa-cubes"
          link="lagerhantering"
        />

        <FunctionCard
          class="func"
          title="Kundsaldon"
          icon="fas fa-id-badge"
          link="kundsaldon"
        />

        <FunctionCard
          class="func"
          title="Verifierade leveranser"
          icon="fas fa-people-carry"
          link="leveranser"
        />

        <FunctionCard
          class="func"
          title="Digitalt växtpass"
          icon="fas fa-leaf"
          link="pass"
        />
      </div>
    </section>
    <!-- Function details -->
    <div class="function-details">
      <Function
        id="lagerhantering"
        :title="functions.function1.title"
        :description="functions.function1.description"
        :image="functions.function1.image"
        direction="right"
      />
      <Function
        id="kundsaldon"
        :title="functions.function2.title"
        :description="functions.function2.description"
        :image="functions.function2.image"
        direction="left"
      />
      <Function
        id="leveranser"
        :title="functions.function3.title"
        :description="functions.function3.description"
        :image="functions.function3.image"
        direction="right"
      />
      <Function
        id="pass"
        :title="functions.function4.title"
        :description="functions.function4.description"
        :image="functions.function4.image"
        direction="left"
      />
    </div>
    <!-- Footer -->
    <section class="footer">
      <p>Bringle 2021</p>
    </section>
  </div>
</template>

<script>
import functions from "~/assets/data/functions.json";
export default {
  data() {
    return {
      functions,
    };
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  overflow-y: scroll;
  background-color: #ece5f0;
}
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

// HERO

.hero {
  position: relative;
  background-repeat: no-repeat;
  width: 100%;
  height: min(56.25vw, 90vh);
  background-image: url("~@/assets/images/desktop-hero.jpg");
  background-size: cover;
  background-position-y: center;

  .hero-content {
    margin-left: 55px;
    width: 45vw;
    position: absolute;
    top: 55%;
    transform: translateY(-55%);
    display: flex;
    flex-direction: column;
    align-items: start;
    h1 {
      font-size: 50px;
      @include primary-bold;
      color: #ddd;
    }

    .btn {
      @include primary-regular;
      text-decoration: none;
      font-size: 20px;
      background-color: #43aa8b;
      color: #333;
      border-radius: 8px;
      box-shadow: $shadow;
      margin-right: 15px;
      padding: 8px;
    }

    .btn:hover {
      background-color: #118ab2;
    }

    #btn-2 {
      background: transparent;
      color: #ddd;
      border: 2px solid rgba(0, 0, 0, 0.247);
      box-shadow: none;
    }

    #btn-2:hover {
      background-color: #118ab2;
    }

    .btn-container {
      margin-top: 20px;
      margin-left: 20px;
      display: flex;
      align-items: center;
    }
  }
}

h1 {
  font-weight: 800;
}

// INTRO

.intro-section {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 50px;
  margin-bottom: 140px;
  .img-container {
    flex: 1;

    #desktop {
      margin-top: 25px;
      max-width: 100%;
      height: auto;
    }

    #mobile {
      display: none;
      margin-top: 25px;
      max-width: 100%;
      height: auto;
    }
  }
  .text-container {
    text-align: center;
    padding: 0 50px;
    flex: 1;
    h3 {
      @include primary-bold;
      font-size: 45px;
    }
    p {
      @include primary-regular;
      padding-top: 25px;
      line-height: 25px;
    }
  }
}

// FUNCTIONS SECTION

.functions-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
  margin-bottom: 100px;
  h3 {
    @include primary-bold;
    text-align: center;
    font-size: 45px;
  }
  .functions {
    margin: 30px 30px;
    display: inline-grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    grid-template-rows: 1fr 1fr;
    grid-gap: 25px;
    p {
      font-size: 17px;
    }
  }
}

// FUNCTION DETAILS

// MEDIA QUERIES

@media only screen and(min-width: 1500px) {
  .hero {
    background-size: cover;
    background-position-y: center;
  }
}

@media only screen and(min-width: 1200px) {
  .functions-section {
    .functions {
      padding: 0;
      display: flex;
      justify-content: space-around;
    }
    .func {
      flex: 1;
    }
  }
}

@media only screen and(max-width: 768px) {
  .hero {
    width: 100%;
    height: 500px;
    background-size: 100vw * 1.8;
    background-position: 95%;

    .hero-content {
      align-items: center;
      margin: 0;
      padding: 0 30px;
      width: 100%;
      text-align: center;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      h1 {
        font-size: 40px;
        text-shadow: 4px 4px 3px rgb(0, 0, 0);
      }
      .btn-container {
        width: 100%;
        padding: 0;
        margin: 0;
        display: flex;
        justify-content: space-around;
      }
      .btn {
        flex: 1;
        font-size: 20px;
        margin: 0;
        padding: 10px;
        margin: 10px;
      }
      #btn-2 {
        background-color: rgba(29, 69, 179, 0.637);
      }
    }
  }

  .main-nav {
    display: none;
  }

  #mobile-nav {
    display: block;
  }

  .intro-section {
    align-items: center;
    flex-direction: column-reverse;
    margin-bottom: 10px;
    .img-container {
      max-width: 70%;
      height: auto;
      margin-top: 10px;

      #desktop {
        display: none;
      }

      #mobile {
        display: block;
      }
    }
    .text-container {
      h3 {
        font-size: 40px;
        margin-top: 18px;
      }
      p {
        padding-top: 10px;
      }
    }
  }

  .functions-section {
    h3 {
      font-size: 40px;
      margin-top: 50px;
    }
  }
}
</style>
