<template>
  <div>
    <button @click="estado = !estado">Cambiar valor</button>
  </div>
  <div><button @click="miobj.count++">Aumentar valor</button></div>
  <div v-show="estado">¡Apareci!</div>
  <div>{{ miobj.count }}</div>
</template>

<script setup>
import { ref, reactive, watch, computed } from "vue";

const estado = ref(true);
const miobj = reactive({ count: 0 });

watch([estado, () => miobj.count], (newValue, oldValue) => {
  console.log("Anterior", oldValue);
  console.log("Nuevo", newValue);
});
</script>
