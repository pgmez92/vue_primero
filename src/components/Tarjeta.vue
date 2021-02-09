<template>
  <div class="row">
    <div class="col-6">
      <img alt="Vue logo" src="../assets/neteroero.svg.png">
    </div>
    <div class="col-6">
      <h3>Titulo</h3>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tenetur
        voluptates nihil vel similique cupiditate laborum incidunt adipisci,
        repellat harum quos, consectetur libero atque ducimus vitae iusto
        assumenda provident! Enim, soluta?
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Tarjeta"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
.row{
  border-style: dotted;
  border-radius: 10px;
  margin: 10px;
  img{
    height: 25%;
  }
}
</style>
