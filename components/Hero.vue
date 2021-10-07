<template>
  <div class="hero">
    <div class="content">
      <h1 class="header">Enkel hantering av CC-kärror</h1>
      <p class="snippet">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil tempora
        ratione dolor sapiente? Repellendus nemo facere aliquid rerum ea non?
      </p>
      <button class="primary-btn">Se video</button>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.hero{
  width: 100%;
  text-align: center;
  background-image: url('~@/assets/images/hero-banner-new.jpg');
  background-size: cover;
  background-position: bottom 0px left 35%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

.content{
  padding-block: max(20vh, 20%);
}

.header{
  margin: 0 20% 0 20%;
}

.primary-btn{
  width: 25%;
  margin: 0 auto 0 auto;
}

.snippet{
  margin: 2vh 20% 5vh 20%;
}
</style>
