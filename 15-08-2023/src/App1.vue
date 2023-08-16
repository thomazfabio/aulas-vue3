<template>
  <div v-if="isLogged">
    <h1>Dashboard</h1>
    <p>Área logada</p>
    <button @click="isLogged = false">Sair</button>
  </div>
<div v-else>
      <h1>Autenticação</h1>
      <p>Faça login</p>
      <input v-model="user.name" type="text" placeholder="Usuário"> 
      <input v-model="user.password" type="password" placeholder="Senha">
      <button @click="login()">Entrar</button>
  </div>

</template>
<script setup>
import { ref } from 'vue'
const isLogged = ref(false);
const user = ref({name:'', password:''})
const login = ref( () => {
  if(user.value.name === 'admin' && user.value.password === '123456')
  isLogged.value = true;
});
</script>
<style>
  
</style>