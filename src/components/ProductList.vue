<script setup>
defineProps(['produtos']);
</script>

<template>
  <table>
    <thead>
      <tr>
        <th>Id</th>
        <th>Nome</th>
        <th>Preço</th>
        <th>Ações</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="produto in produtos" :key="produto.id">
        <td>{{ produto.id }}</td>
        <td>{{ produto.nome }}</td>
        <td>R$ {{ produto.preco }}</td>
        <td>
          <i class="mdi mdi-delete" @click="$emit('excluir', produto.id)" />
        </td>

      </tr>
    </tbody>
  </table>
</template>

<style scoped>
table {
  width: 50%;
  border-collapse: collapse;
}

th,
td {
  border: 1px solid gray;
  padding: 10px;
}

th {
  background-color: lightgray;
}

tr {
  text-align: center;
}

tr i {
  cursor: pointer;
  font-size: larger;
}
</style>