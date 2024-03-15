<script setup>
  //Importando una funcion para crear referencias reactivas
  import { ref } from 'vue'

  //Creando una referencia reactiva de tipo string
  const header = ref('App lista de compras');
  const shoppingIcon = ref("material-icons shopping-cart-icon")

  //Creando una referencia reactiva para almacenar el valor de la lista
  const items = ref([
  // {id: 0 , label: 'Leche'},
  // {id: 1 , label: 'Arroz'},
  // {id: 2 , label: 'Carne'},
  // {id: 3 , label: 'Pan'},
  // {id: 4 , label: 'Huevos'}
  ]);

  const newItem = ref('');
  const newItemHighPriority = ref(false)

  const selectButton = ref(false)

  //Metodos, son funciones de javascript
const saveItems = () => {
  //Agrega un nuevo elemento a la lista proveniente de la caja de texto
  items.value.push({ id: items.value.length, label: newItem.value})

  //Borramos el contenido de la caja de texto
  newItem.value = "";
};

//Entrega Condicional Tema
</script>

<template>
  <!-- Header -->
  <div class="header">
    <h1> 
      <i :class="shoppingIcon">local_mall</i>{{ header }}
    </h1>
    <button class="btn" @click="selectButton = false">Cancelar</button>
    <button class="btn" @click="selectButton = true">Agregar Articulo</button>
  </div>

  <!-- Formulario -->
  <form
    v-if="selectButton"
    v-on:submit.prevent="saveItems"
    class="add-item form">
    <input 
    v-model ="newItem" type="text" 
    placeholder="Agregar Articulo">

    <!-- Checkbox -->
    <label>
      <input type="checkbox" v-model="newItemHighPriority">
      Alta Prioridad
    </label>

    <!-- Boton -->
    <button 
      class="btn btn-primary">
      Agregar Articulo
    </button>
  </form>

  <!-- Entrega de Lista -->
  <ul>
    <li v-for="({ id, label }, i) in items" v-bind:key="id">🌟 {{ i }} {{ label }}</li>
  </ul>

  <!-- Mensaje Condicional -->
  <p v-if="items.length === 0">🥀 No hay elementos en la lista 🥀</p>
</template>

<style scoped>
.shopping-cart-icon{
  font-size: 2rem;
}
</style>
