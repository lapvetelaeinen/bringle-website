<template>
  <div class="container">
    <h2>Bringles funktioner</h2>
    <div class="functions-container">
      <FunctionCard title="Saldo på kärror" icon="fab fa-accessible-icon"/>
      <FunctionCard title="Verifiering av leveranser" icon="fab fa-accessible-icon"/>
      <FunctionCard title="Leveranshistorik" icon="fab fa-accessible-icon"/>
      <FunctionCard title="Elektroniska växtpass" icon="fab fa-accessible-icon"/>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.container{
    background-color: rgb(166, 219, 255);
    text-align: center;
    font-size: 25px;
    padding-block: 5vh;
}
.functions-container{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  padding-bottom: 20px;
}

</style>
