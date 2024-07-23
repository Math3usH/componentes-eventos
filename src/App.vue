<script setup>
import { ref } from 'vue';
import ProductList from '@/components/ProductList.vue';
import FormAdd from '@/components/FormAdd.vue';


function adicionarProduto(dado) {
  perfil.value.push(dado);
  ;
}
const perfil = ref([])

</script>

<template>
  <h1>Meus produtos</h1>
  <form-add @adicionar="adicionarProduto" />
  <product-list 
  :perfil="perfil" 
/>
</template>

<style scoped></style>