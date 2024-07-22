<script setup>
import { ref } from 'vue';
import ProductList from '@/components/ProductList.vue';
import ProductAdd from '@/components/ProductAdd.vue';

const produtos = ref([
  { id: 1, nome: 'Produto 1', preco: '20,50' },
  { id: 2, nome: 'Produto 2', preco: '120,50' },
  { id: 3, nome: 'Produto 3', preco: '220,50' },
  { id: 4, nome: 'Produto 4', preco: '320,50' },
]);
const proxId = ref(5);

function excluir(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id);
  produtos.value.splice(index, 1);


}

function adicionarProduto(produto) {
  produto.id = proxId;
  produtos.value.push(produto);
  proxId.value++;
}
</script>

<template>
  <h1>Meus produtos</h1>
  <product-add @adicionar="adicionarProduto" />
  <product-list 
  :produtos="produtos" 
  @excluir="excluir" 
  @apagarTudo="excluirTodos" />
</template>

<style scoped></style>