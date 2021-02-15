<template>
  <Input campo="DNI" expresion="([a-z]|[A-Z]|[0-9])[0-9]{7}([a-z]|[A-Z]|[0-9])" />
</template>

<script>
import Input from "@/components/Input";
export default {
  name: "Ejercicio2",
  components: {
    Input,
  },
};
</script>

<style>
</style>