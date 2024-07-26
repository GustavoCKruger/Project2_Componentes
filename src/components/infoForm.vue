<script setup>

const props = defineProps(['usuario'])

const usuario = props.usuario;

const emits = defineEmits(['voltar']);

function voltarDados() {
    emits('voltar')
}

</script>

<template>
    <div class="container">

        <h2>Informações do usuario</h2>
        <div class="form">
            <br>
            <p>Nome: {{ usuario.nome }}</p>
            <p>Email: {{ usuario.email }}</p>
            <p>Senha: {{ usuario.senha }}</p>
            <p>Confirmação de Senha: {{ usuario.confirmSenha }}</p>
            <p>Cidade: {{ usuario.cidade }}</p>
            <p>Hobbies: {{ usuario.hobbies }}</p>
            <p>Linguagem: {{ usuario.linguagemPref }}</p>
            <p>Biografia: {{ usuario.bio }}</p>
        </div>
        <div class="botao">
            <button class="botao" type="submit" @click="voltarDados()">voltar</button>
        </div>
    </div>


</template>

<style scoped>
.container {
    border: 2px solid black;
    min-width: 80%;
    min-height: 750px;
    margin-left: 300px;
    border-radius: 20px;
    background-color: dodgerblue;
}

body {
    font-size: 40px;
}

main {
    margin-left: 80px;
    margin-top: 30px;
}

.form {
    margin: 40px 0px 0px 15vh;
}

h2 {
    margin: 30px 0 10px 40px;
}


.form-select {
    margin-top: 10px;
    margin-bottom: 10px;
    background-color: gray;
    min-width: 20px;
    min-height: 20px;
    border: 2px solid black;
    border-radius: 20px;
}

.check {
    border: 4px solid black;
    min-width: 10px;
}

button {
    min-height: 20px;
    min-width: 40px;
    margin: 20px 0 0 40vh;
    border: 2px solid black;
    background-color: blue;
    color: aliceblue;
}

.form-enter-active,
.form-leave-active {
    transition: opacidade 0.5s ease;
}
</style>