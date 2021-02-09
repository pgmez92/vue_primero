<template>
  <div class="row">
    <div class="col-12">
      <img alt="Vue logo" src="@/assets/neteroero.svg.png" />
      <p>Fuerza actual: {{ fuerzaActual }}</p>
      <button @click="incrementarFuerza">Incrementar fuerza</button>
    </div>
  </div>
</template>

<script>
import {ref} from "vue"

export default {
  name: "Personaje",
  props: {
    fuerza: {
      type: String,
      default: 5,
      required: true,
    },
  },
  setup(props) {
    let fuerzaActual = ref(props.fuerza);
    const incrementarFuerza = () => {
      fuerzaActual.value++;
    };
    return {
      fuerzaActual,
      incrementarFuerza,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
.row {
  border-style: dotted;
  border-radius: 10px;
  margin: 10px;
  img {
    height: 25%;
  }
}
</style>
