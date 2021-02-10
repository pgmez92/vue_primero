<template>
  <div class="about">
    <h1>Estás en Ejemplo</h1>
    <Personaje fuerza="5" foto="logo.png"/>
    <Personaje fuerza="10" foto="neteroero.svg.png" />
  </div>
</template>

<script>
// @ is an alias to /src
import Personaje from "@/components/Personaje.vue";

export default {
  name: "Ejemplo",
  components: {
    Personaje,
  },
};
</script>