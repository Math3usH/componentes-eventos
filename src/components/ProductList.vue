<script setup>
defineProps(['produtos'])
</script>

<template>
<table>
    <thead>
      <tr>
        <th>ID</th>
        <th>Nome</th>
        <th>Preço</th>
        <th>Ações</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="produtos in produtos" :key="produtos.id">
        <td>{{ produtos.id }}</td>
        <td>{{ produtos.nome }}</td>
        <td>{{ produtos.preco }}</td>
        <td><i class="mdi mdi-delete" @click="$emit('excluir')" /></td>
      </tr>
    </tbody>
  </table>
</template>