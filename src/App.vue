<script setup>
//Importando una funcion para crear referencias reactivas
import { ref } from 'vue'
//Creando una referencia reactiva de tipo string
const header = ref('App lista de compras');
const shoppingIcon = ref('material-icons shopping-cart-icon');
//const bag = ref('<i class="material-icons shopping-cart-icon">local_mall</i>')
</script>

<template>
  <h1> <i :class="shoppingIcon">local_mall</i>{{ header }}</h1>
</template>

<style scoped>
.shopping-cart-icon{
  font-size: 2rem;
}
</style>