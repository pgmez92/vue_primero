<template>
  <p>soy reactivo</p>
  <p>{{ contador }}</p>
  <button @click="sumar">+</button>
</template>

<script>
import {ref} from "vue";

export default {
  name: "Reactividad",
  props: {},
  setup() {
    let contador = ref(0);
    const sumar = () => {
      contador.value++;
      console.log(contador);
    };
    return {
      contador,
      sumar,
    };
  },
};
</script>

<style>
</style>