<template>
  <div class="home">
    <Tarjeta />
    <Tarjeta />
  </div>
</template>

<script>
// @ is an alias to /src
import Tarjeta from "@/components/Tarjeta.vue";

export default {
  name: "Home",
  components: {
    Tarjeta,
  },
};
</script>
