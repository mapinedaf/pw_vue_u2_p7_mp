<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Contador
    encabezado="Contador primero"
    :valor="calcular(1, 3)"
    v-bind:esVerdad="muestra",
    :valor2 = 78
  ></Contador>
  <Contador
    encabezado="Contador Segundo"
    v-bind:valor="5 + 1"
    :esVerdad="muestra2"
  ></Contador>
  <button @:click="cambiar(1)">Cambiar Primero</button>
  <button @:click="cambiar(2)">Cambiar Segundo</button>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Contador from "./components/Contador.vue";

export default {
  name: "App",
  data() {
    return {
      muestra: true,
      muestra2: true,
    };
  },
  components: {
    HelloWorld,
    Contador,
  },
  methods: {
    calcular(a, b) {
      return a + b;
    },
    cambiar(a) {
      if (a === 1) {
        this.muestra = !this.muestra;
      } else {
        this.muestra2 = !this.muestra2;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
