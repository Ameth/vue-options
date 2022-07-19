<!-- eslint-disable vue/no-parsing-error -->
<template>
  <button @click="show = !show">Menú</button>
  <transition name="fade">
    <Menu v-show="show" />
  </transition>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
// import { defineAsyncComponent } from "vue";

// const HelloWorld = defineAsyncComponent(() =>
//   import("./components/HelloWorld.vue")
// );

import Menu from "@/components/Menu.vue";

export default {
  name: "App",
  data() {
    return {
      show: false,
    };
  },
  components: { Menu },
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

.fade-enter-from {
  opacity: 0;
}

.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}
</style>
