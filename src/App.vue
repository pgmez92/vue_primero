<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/pruebas">Pruebas</router-link> |
    <router-link to="/ejemplo">Ejemplo</router-link> |
    <router-link to="/ejercicio1">Reactividad</router-link> |
    <router-link to="/ejercicio2">Validacion DNI</router-link> |
    <router-link to="/ejercicio3">Login</router-link> |
    <router-link to="/ejercicio4">Tabla</router-link> |
    <router-link to="/ejercicio5">Provincias</router-link> |
    <router-view />
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
