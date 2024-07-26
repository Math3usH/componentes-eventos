<script setup>
import { ref } from 'vue';
import ProductList from '@/components/ProductList.vue';
import FormAdd from '@/components/FormAdd.vue';

const isOpen = ref(false)

function adicionarProduto(dado) {
  isOpen.value = true
    perfil.value.push(dado);
  ;
}
const perfil = ref([])


</script>

<template>
  <h1>Formulario</h1>
  <form-add @adicionar="adicionarProduto" />
  <div v-if="isOpen">
  <product-list 
  :perfil="perfil" 
/>
</div>
</template>

<style scoped>
  h1 {
    font-size: 2.5em;
    font-weight: bold;
    color: #333;
    margin-bottom: 1em;
    text-align: center;
  }

</style>