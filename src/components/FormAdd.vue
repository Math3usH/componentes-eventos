<script setup>
  import { reactive } from 'vue';
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
      <input type="text" id="estado" v-model="perfil.estado">
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