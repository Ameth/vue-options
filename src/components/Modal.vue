<template>
  <div>
    <button @click="toggle">Abrir Modal</button>
    <teleport to="body">
      <div v-show="show" class="modal">
        <h1>Titulo</h1>
        <p>Contenido modal</p>
        <button @click="toggle">Cerrar</button>
      </div>
    </teleport>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    };
  },
  methods: {
    toggle() {
      this.show = !this.show;
    },
  },
};
</script>

<style scoped>
.modal {
  display: block;
  opacity: 0.8;
  background-color: darkgrey;
}
</style>