<script setup>
defineProps(['perfil']);
</script>

<template>
  <table>   
   <thead>
      <tr>
        <th>Nome</th>
        <th>Email</th>
        <th>Senha</th>
        <th>Data de nascimento</th>
        <th>Cidade</th>
        <th>Estado</th>
        <th>Estado civil</th>
        <th>Excluir</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(perfil, index) in perfil" :key="index">
        <td>{{ perfil.nome }}</td>
        <td>{{ perfil.email }}</td>
        <td>{{ perfil.senha }}</td>
        <td>{{ perfil.dataNascimento }}</td>
        <td>{{ perfil.estado }}</td>
        <td>{{ perfil.cidade }}</td>
        <td>{{ perfil.estadoCivil }}</td>

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