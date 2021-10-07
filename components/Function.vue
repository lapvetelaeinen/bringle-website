<template>
  <div>
    <div class="container" :class="direction">
      <div class="text-box">
        <h3>{{ title }}</h3>
        <p>{{ description }}</p>
      </div>
      <img :src="require('@/assets/images/' + image + '')" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    image: String,
    description: String,
    direction: String,
  },
}
</script>

<style lang="scss" scoped>
.container {
  margin-bottom: 100px;
  margin-left: 20px;
  margin-right: 20px;
  text-align: center;
}
h3 {
  @include primary-bold;
  font-size: 40px;
}
p {
  @include primary-regular;
  margin-top: 15px;
}
img {
  margin-top: -20px;
  width: 50%;
  height: auto;
}

@media only screen and(min-width: 768px) {
  .container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-auto-rows: minmax(150px, auto);
    grid-gap: 20px;
    grid-template-areas: 'image title';
    margin-bottom: 140px;
  }
  .text-box {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  h3 {
    grid-area: title;
  }
  p {
    grid-area: title;
  }
  img {
    grid-area: image;
    width: 100%;
  }

  .left {
    grid-template-areas: 'title image';
  }
}
</style>
