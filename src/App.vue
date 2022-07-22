<!-- eslint-disable vue/no-parsing-error -->
<template>
  <input type="text" name="" id="" v-model="mensaje" />
  <Home :texto="text" />
</template>

<script setup>
import Home from "@/components/Home.vue";
import { provide, ref } from "vue";

const text = "Dato que viene de una variable por props";

const mensaje = ref("");

provide("mensaje", mensaje);

// export default {
//   name: "App",
//   components: {
//     Home,
//   },
// };
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
