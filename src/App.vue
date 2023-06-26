<template>
  <div>
    <p>Contador: {{ count }}</p>
    <p>Contador Doble: {{ doubledCount }}</p>
    <button @click="increment">Incrementar</button>
  </div>
</template>

<script>
import { ref, computed, onMounted } from 'vue';

export default {
  setup() {
    // Definición de variables reactivas
    const count = ref(0);
    
    // Definición de método
    const increment = () => {
      count.value++;
    };
    
    // Definición de propiedad computada
    const doubledCount = computed(() => count.value * 2);
    
    // Hook de montaje
    onMounted(() => {
      console.log('El componente ha sido montado.');
    });
    
    // Retorno de variables y funciones
    return {
      count,
      increment,
      doubledCount
    };
  }
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
