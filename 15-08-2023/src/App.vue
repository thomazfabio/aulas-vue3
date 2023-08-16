<template>
   <div  id="todo">
  <div>
    <h1>Exercicio 1</h1>
    <p>Usando V-if e v-else faça os seguintes blocos</p>
    <ul>
      <li>um bloco para logar no sistema</li>
      <li>um bloco para cadastro de usuario e senha</li>
      <li>um bloco para area logada</li>
    </ul>
    <p>usuario deve ser salvo em um vetor, deve ser multi usuarios</p>
  </div>
  <hr>
  <div v-if="isLogged">
    <h1>Area restrita</h1>
  </div>
  <div v-else-if="newUser">
    <h1>cadastro</h1>
    <input type="text" placeholder="usuario">
    <input type="text" placeholder="senha"><br>
    <button>cadastrar</button>
  </div>
  <div v-else>
    <h1>Login no Sistema</h1>
    <input type="text" placeholder="usuario">
    <input type="text" placeholder="senha"><br>
    <button>logar</button><br>
    <button @click="newUser = true">cadastrar</button>
  </div>
</div>
</template>

<script setup>
import { ref } from 'vue'
const isLogged = ref(false)
const newUser = ref(false)
const users = ref([])
const add = () => {
  users.value.push({
    usuario: 'usuario',
    senha: 'senha'
  })
}
</script>

<style>
#todo {
  margin: 0 auto;
  width: 100%;
  
}
</style>