<template>
  <div v-if="!logeado" class="container">
    <Input v-model="usuario" campo="Usuario" expresion="(pepe)" flags_expresion="giu" />
    <Input v-model="password" class="pwd" campo="Contraseña" expresion="(1234)" />
    <button @click="iniciarSesion">pulsame</button>
  </div>

  <div v-else class="container">
    <p>YEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE</p>
  </div>

</template>

<script>
import Input from "@/components/Input";
import {ref} from "vue"; 

export default {
  name: "Pruebas",
  props:{
      logeado:{
          type:boolean,
          default:false
      }
  },
  components: {
    Input,
  },
  setup(props){
      let logeado=ref(props.logeado)
      const iniciarSesion=()=>{
          console.log(usuario.value)
          console.log(password.value)
      }
      return{
          logeado,
          iniciarSesion
      }
  }
};
</script>

<style>
.container {
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
}
</style>