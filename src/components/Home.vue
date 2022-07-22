<template>
  <div>
    {{ texto }}<br />
    <button @click="estado = !estado" ref="btn">Cambiar valor</button>
    <div><button @click="miobj.count++">Aumentar valor</button></div>
    <div><button @click="proximo = 0">Resetear</button></div>
    <div v-show="estado">¡Apareci!</div>
    <div>{{ miobj.count }}</div>
    <div>Siguiente valor: {{ proximo }}</div>
    <div>Mensaje del abuelo: {{ mensaje }}</div>
  </div>
</template>

<script setup>
import { ref, reactive, watch, computed, inject, onMounted } from "vue";

const props = defineProps({
  texto: String,
});

const estado = ref(true);
const miobj = reactive({ count: 0 });

const mensaje = inject("mensaje", "Mensaje por defecto");

const btn = ref(null);

onMounted(() => {
  console.log(btn.value);
});

// const proximo = computed(() => miobj.count + 1);

const proximo = computed({
  get: () => miobj.count + 1,
  set: (valor) => {
    miobj.count = valor;
  },
});

watch(proximo, (newValue, oldValue) => {
  console.log("Anterior", oldValue);
  console.log("Nuevo", newValue);
  if (miobj.count > 10) {
    proximo.value = 0;
  }
});
</script>
