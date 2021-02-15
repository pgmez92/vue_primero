<template>
  <div class="row">
    <div class="inputForm">
      <label :class="clases">{{ campo }}</label>
      <input @keyup="comprobarCampo" type="text" />
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "Input",
  props: {
    campo: {
      type: String,
      default: "Campo",
    },
    expresion: {
      type: String,
    },
    flags_expresion: {
      type: String,
    },
  },
  setup(props) {
    let clases = ref("bad");

    const comprobarCampo = (e) => {
      let texto = e.target.value;
      let validator = new RegExp(props.expresion, props.flags_expresion);

      if (validator.test(texto)) {
        clases.value = "ok";
      } else {
        clases.value = "bad";
      }
    };
    return {
      clases,
      comprobarCampo,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.inputForm {
  margin-right: 10px;
}

.bad {
  background-color: red;
}
.ok {
  background-color: green;
}
</style>
