<script setup>
  import { reactive, ref } from 'vue';
  import {estados} from "./estados.js"
  const estadosAll = ref(estados)
  const emit = defineEmits(['adicionar']);
  const perfil = reactive({
    nome: '',
    email: '',
    senha: '',
    dataNascimento: '',
    estado: '',
    cidade: '',
    estadoCivil: ''
  });
  function salvar() {
    if (perfil.nome === '' || perfil.email === '' || perfil.senha === '' || perfil.dataNascimento === '' || perfil.estado === '' || perfil.cidade === '' || perfil.estadoCivil === '') {
      alert('Os campos acima são obrigatórios');
      return;
    }
    emit('adicionar',{...perfil} );
  }
</script>
<template>
  <form @submit.prevent="salvar">
    <div>
      <label for="nome">Nome</label>
      <input type="text" id="nome" v-model="perfil.nome" />
    </div>
    <div>
      <label for="email">Email</label>
      <input type="email" id="email" v-model="perfil.email" />
    </div>
    <div>
      <label for="senha">Senha</label>
      <input type="password" id="senha" v-model="perfil.senha">
    </div>
    <div>
      <label for="dataNascimento">Data de Nascimento</label>
      <input type="date" id="dataNascimento" v-model="perfil.dataNascimento">
    </div>
    <div>
      <label for="estado">Estado</label>
      <select v-model="perfil.estado" id="estado">
      <option value="" disabled>selecione um estado</option>
      <option v-for="estado in estados" :key="estado.UF" :value="estado.nome">
        ({{ estado.nome }}) {{ estado.UF }}
      </option>
      </select>

    </div>
    <div>
      <label for="cidade">Cidade</label>
      <input type="text" id="cidade" v-model="perfil.cidade">
    </div>
    <div>
      <label for="estadoCivil">Estado Civil</label>
      <input type="text" id="estadoCivil" v-model="perfil.estadoCivil">
    </div>
    
    
    <button type="submit">Salvar</button>
  </form>
</template>

<style scoped>
  form {
    max-width: 600px;
    margin: 0 auto;
    padding: 1em;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    background-color: #f9f9f9;
  }

  div {
    margin-bottom: 1em;
  }

  label {
    display: block;
    margin-bottom: 0.5em;
    font-weight: bold;
    color: #333;
  }

  input[type="text"],
  input[type="email"],
  input[type="password"],
  input[type="date"],
  select {
    width: 100%;
    padding: 0.5em;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }

  input[type="text"]:focus,
  input[type="email"]:focus,
  input[type="password"]:focus,
  input[type="date"]:focus,
  select:focus {
    border-color: #007bff;
    outline: none;
  }

  button {
    background-color: #007bff;
    color: #fff;
    padding: 0.7em;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1em;
  }

  button:hover {
    background-color: #0056b3;
  }

  option {
    padding: 0.5em;
  }
</style>
