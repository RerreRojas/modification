<template>
  <ModificarCuadro />
</template>

<script>
import ModificarCuadro from './components/ModificarCuadro.vue';

export default {
  name: 'App',
  components: {
    ModificarCuadro,
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  background-color: black;
}

main {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
