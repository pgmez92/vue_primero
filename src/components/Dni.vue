<template>
  <div class="row">
    <div class="col-6">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tenetur
        voluptates nihil vel similique cupiditate laborum incidunt adipisci,
        repellat harum quos, consectetur libero atque ducimus vitae iusto
        assumenda provident! Enim, soluta?
      </p>
      <label :class="clases">{{ campo }}</label>
      <input @keypress="probarDni" type="text" />
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "Dni",
  props: {
    campo: {
      type: String,
      default: "DNI",
    },
  },
  setup() {
    let clases = ref("bad");

    const probarDni = (e) => {
      let texto=e.target.value;
      let expresion = /([a-z]|[A-Z]|[0-9])[0-9]{7}([a-z]|[A-Z]|[0-9])/;
      if(texto==""){
        return;
      }
      if (texto.length==9 && expresion.test(texto)) {

        clases.value = "ok";
      }else{
        clases.value = "bad";
      }  
      console.log("esto es length: "+texto.length)  
      console.log("esto es lo del input: "+texto)  
    };
    return {
      clases,
      probarDni
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.row {
  border-style: dotted;
  border-radius: 10px;
  margin: 10px;
}
.bad {
  background-color: red;
}
.ok {
  background-color: green;
}
</style>
