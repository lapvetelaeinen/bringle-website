<template>
  <div
    class="function"
    :class="{ active: hover }"
    @mouseover="hover = true"
    @mouseleave="hover = false"
    @click="testFunction"
  >
    <div>
      <i :class="icon"></i>
      <p>{{ title }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    icon: String,
    title: String,
    link: String,
  },
  data() {
    return {
      hover: false,
    };
  },
  methods: {
    testFunction() {
      const element = document.getElementById(this.link);
      element.scrollIntoView({ behavior: "smooth", block: "center" });
    },
  },
};
</script>

<style lang="scss" scoped>
a {
  text-decoration: none;
}
.function {
  cursor: pointer;
  background-color: #f7f7f7;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  text-align: center;
  border-radius: 15px;
  box-shadow: $shadow;
  padding: 20px;

  i {
    font-size: 100px;
    color: #0a5770;
    margin-bottom: 20px;
  }

  p {
    font-size: 20px;
    color: #0a5770;
    @include primary-regular;
  }
}
.active {
  background-color: #118ab2;
}
</style>
