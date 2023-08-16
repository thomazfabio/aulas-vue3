<template>
    <div v-if="isLogged">
        <h1>Área logada</h1>
        <p> Seja bem vindo {{ user.name }} </p>
        <button @click="isLogged = false">Sair</button>
    </div>
    <div v-else-if="isNewUser">
        <h1>Cadastro</h1>
        <input type="text" v-model="user.name" placeholder="Usuário">
        <input type="password" v-model="user.pass" placeholder="Senha">
        <button @click="add()">Cadastrar</button>
    </div>
    <div v-else>
        <h1>Autenticação</h1>
        <input type="text" v-model="user.name" placeholder="Usuário">
        <input type="password" v-model="user.pass" placeholder="Senha">
        <button @click="login()">Logar</button> ou 
        <button @click="isNewUser = true">Cadastrar</button>
    </div>
</template>
<script setup>
import { ref } from 'vue'
const isLogged = ref(false);
const isNewUser = ref(false);
const user = ref({ name: '', pass: '' });
const users = ref([]);
const add = () => {
    users.value.push(user.value);
    user.value = { name: '', pass: '' };
    isNewUser.value = false;
}
const login = () => {
    users.value.find( element => {
        if(element.name == user.value.name 
        && element.pass == user.value.pass) {
            isLogged.value = true;
            user.value = { name: '', pass: '' };
            return;
        }
    });
}

</script>