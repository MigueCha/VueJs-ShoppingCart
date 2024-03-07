<script setup>
//Importando una funcion para crear referencias reactivas
import { ref } from 'vue'
//Creando una referencia reactiva de tipo string
const header = ref('App lista de compras');
const items = ref([
  {id: 1, label: '10 Bolillos'},
  {id: 2, label: '1 Lata de Frijoles'},
  {id: 3, label: '1 Lata de Atun'}
]);
//const bag = ref('<i class="material-icons shopping-cart-icon">local_mall</i>')
//Creando una referencia reactiva para almacenar el valor de la lista
/*const items = ref([
{id: 0, label: 'Leche'},
{id: 1, label: 'Arroz'},
{id: 2, label: 'Carne'},
{id: 3, label: 'Pan'},
{id: 4, label: 'Huevos'}
]);*/
</script>

<template>
  <h1> <i class="material-icons shopping-cart-icon">local_mall</i>{{ header }}</h1>
  <ul>
    <li v-for="{ id, label } in items" v-bind:key="id">🔹 {{ label }}</li>
  </ul>
</template>

<style scoped>
.shopping-cart-icon{
  font-size: 2rem;
}
</style>