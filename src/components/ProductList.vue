<script setup>
import SvgIcon from '@jamescoyle/vue-icon';

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
        <td>{{ perfil.cidade }}</td>
        <td>{{ perfil.estado }}</td>
        <td>{{ perfil.estadoCivil }}</td> 
        <td>X</td>
      </tr>
    </tbody>
  </table>
</template>


<style scoped>
  /* Estilo para o contêiner da página */
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2em;
    background-color: #f9f9f9;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }

  /* Estilo para a tabela */
  table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 1em;
  }

  th,
  td {
    border: 1px solid #ddd;
    padding: 12px;
    text-align: left;
  }

  th {
    background-color: #d4d4d49d; 
    color: rgb(0, 0, 0);
  }

  tr:nth-child(even) {
    background-color: #f2f2f2;
  }

  tr:hover {
    background-color: #ddd; 
  }

  th:last-child,
  td:last-child {
    text-align: center;
  }

</style>