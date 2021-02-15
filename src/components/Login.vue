<template>
  <div v-if="!logeado" class="container">
    <Input
      id="campo"
      campo="Usuario"
      expresion="(pepe)"
      flags_expresion="giu"
    />
    <Input id="pwd" class="pwd" campo="Contraseña" expresion="(1234)" />
    <button @click="login">Iniciar sesión</button>
  </div>
  <div v-else>
    <p>YEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE</p>
    <button @click="unlogin">BIEEEEEEEEEEEEEEEEN</button>
  </div>
</template>

<script>
import Input from "@/components/Input";
import { ref, reactive, onMounted } from "vue";
export default {
  name: "Login",
  components: {
    Input,
  },
  props: {},
  setup() {
    let logeado = ref(false);
    let validatorUser = new RegExp("(pepe)", "giu");
    let validatorPwd = new RegExp("(1234)");
    const login = () => {
      if (
        validatorUser.test(campo.lastChild.lastChild.value) &
        validatorPwd.test(pwd.lastChild.lastChild.value)
      ) {
        logeado.value = true;
      }
    };
    const unlogin = () => {
      logeado.value = false;
    };

    return {
      logeado,
      login,
      unlogin,
    };
  },
};
</script>

<style scoped>
.container {
  margin: 0 auto;
  margin-top: 20px;
  padding: 20px;
  border-radius: round;
  border-style: double;
  border-color: black;
  color: black;
  background-color: darkslateblue;
  font-size: medium;
  font-weight: bold;
  width: 50%;
  align-content: center;
}
.pwd {
  font-style: italic;
  margin-top: 10px;
}
</style>