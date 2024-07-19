<script setup>
import { ref } from 'vue';

import ProductList from '@/components/ProductList.vue'

const produtos = ref([
  {id:1, nome: "Produto A", preco: "R$199,00" },
  {id:2, nome: "Produto B", preco: "R$299,00" },
  {id:3, nome: "Produto C", preco: "R$399,00" },
  {id:4, nome: "Produto D", preco: "R$499,00" }
])

function excluirProduto() {
  const index = produtos.value.findIndex((produtos) => produtos.id === id)
  produtos.value.splice(index, 1)
}

</script>

<template>
  <h1>meus produtos</h1>
  <productAdd @salvar="adicionarProduto"/>
  <ProductList :produtos="produtos" @="excluir=excluirProduto" />
</template>

<style scoped>

</style>
