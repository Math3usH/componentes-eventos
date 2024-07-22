<script setup>
  import { reactive } from 'vue';
  const emit = defineEmits(['adicionar']);
  const produto = reactive({
    nome: '',
    preco: '',
  });
  function salvar() {
    if (produto.nome === '' || produto.preco === '') {
      alert('Os campos nome e preço são obrigatórios');
      return;
    }
    emit('adicionar',{...produto} );
  }
</script>
<template>
  <form @submit.prevent="salvar">
    <div>
      <label for="nome">Nome</label>
      <input type="text" id="nome" v-model="produto.nome" />
    </div>
    <div>
      <label for="preco">Preço</label>
      <input type="text" id="preco" v-model="produto.preco" />
    </div>
    <button type="submit">Salvar</button>
  </form>
</template>