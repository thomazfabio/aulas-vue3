<template>
  <div>
    <h1>Cadastro de Clientes</h1>
    <input type="text" placeholder="Nome Completo"><br>
    <input type="text" placeholder="Cpf"><br>
    <input type="text" placeholder="Email"><br>
    <button >Salvar</button>

    <h1>ola mundo</h1>
    <p>Meu nome é: {{ nome }}</p>
    <p>Meu completo é: {{ nomeCompleto }}</p>
    <button @click="calcular">Calcular</button>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
const nome = ref('Fabio');
const sobrenome = ref('Thomaz');
const calcular = ref(() => {
  console.log('calculando...');
});
const nomeCompleto = computed(() => {
  return nome.value + ' ' + sobrenome.value;
});
</script>