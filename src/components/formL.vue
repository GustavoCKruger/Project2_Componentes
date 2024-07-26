<script setup>
import { ref } from 'vue'

const props = defineProps([
    'dados'
])
const usuario = ref({
    ...props.dados,
    hobbies: []
})

const emits = defineEmits([
    'submit'
])

function enviarDados() {
    emits('submit', usuario.value)
}

</script>

<template>
    <title>Form.2info2.GustavoCKruger</title>
    <div class="container">
        <main>
            <h1>Editor de Perfil</h1>
            <form @submit.prevent="enviarDados">
                <div class="row">
                    <label for="nomeField" class="formLabel">Nome</label>
                    <br>
                    <input type="text" class="formInput" id="nome" v-model="usuario.nome" required />
                </div>
                <div class="row">
                    <label for="emailField" class="formLabel">E-mail</label>
                    <div class="input-group">
                        <input type="email" class="formInput" id="email" v-model="usuario.email" required />
                    </div>
                    <div class="row">
                        <label for="senha">Senha</label>
                        <br>
                        <input type="password" id="senha" v-model="usuario.senha" required>
                    </div>
                    <div class="row">
                        <label for="confirmSenha">Confirme a senha</label>
                        <br>
                        <input type="password" id="confirmSenha" v-model="usuario.confirmSenha" required>
                    </div>
                </div>
                <div class="select">
                    <label for="cidadeField" class="formLabel">Cidade</label>
                    <br>
                    <input type="text" class="formInput" id="cidadeField" v-model="usuario.cidade" required>
                </div>
                <div class="select">
                    <label for="estadoField" class="formLabel">Estado</label>
                    <br>
                    <select class="form-select" id="estadoField" v-model="usuario.estado">
                        <option selected disabled value="">Selecionar...</option>
                        <option value="AC">Acre</option>
                        <option value="AL">Alagoas</option>
                        <option value="AP">Amapá</option>
                        <option value="AM">Amazonas</option>
                        <option value="BA">Bahia</option>
                        <option value="CE">Ceará</option>
                        <option value="DF">Distrito Federal</option>
                        <option value="ES">Espírito Santo</option>
                        <option value="GO">Goiás</option>
                        <option value="MA">Maranhão</option>
                        <option value="MT">Mato Grosso</option>
                        <option value="MS">Mato Grosso do Sul</option>
                        <option value="MG">Minas Gerais</option>
                        <option value="PA">Pará</option>
                        <option value="PB">Paraíba</option>
                        <option value="PR">Paraná</option>
                        <option value="PE">Pernambuco</option>
                        <option value="PI">Piauí</option>
                        <option value="RJ">Rio de Janeiro</option>
                        <option value="RN">Rio Grande do Norte</option>
                        <option value="RS">Rio Grande do Sul</option>
                        <option value="RO">Rondônia</option>
                        <option value="RR">Roraima</option>
                        <option value="SC">Santa Catarina</option>
                        <option value="SP">São Paulo</option>
                        <option value="SE">Sergipe</option>
                        <option value="TO">Tocantins</option>
                    </select>
                </div>
                <div class="lista">
                    <p class="selected">Hobbies</p>
                    <input class="check" type="checkbox" id="hobbies" value="esportes" v-model="usuario.hobbies" />
                    <label for="hobbies">Esportes</label>
                    <input class="check" type="checkbox" id="hobbies" value="música" v-model="usuario.hobbies" />
                    <label for="hobbies">Música</label>
                    <input class="check" type="checkbox" id="hobbies" value="viagens" v-model="usuario.hobbies" />
                    <label for="hobbies">Viagens</label>
                    <input class="check" type="checkbox" id="hobbies" value="leitura" v-model="usuario.hobbies" />
                    <label for="hobbies">Leitura</label>
                </div>
                <div class="lista">
                    <p class="selected">Linguagem preferida</p>
                    <input class="check" type="radio" v-model="usuario.linguagemPref" value="C" id="langC" />
                    <label for="langC">C</label>
                    <input class="check" type="radio" v-model="usuario.linguagemPref" value="Java" id="langJava" />
                    <label for="langJava">Java</label>
                    <input class="check" type="radio" v-model="usuario.linguagemPref" value="Python" id="langPython" />
                    <label for="langPython">Python</label>
                    <input class="check" type="radio" v-model="usuario.linguagemPref" value="Javascript" id="langJs" />
                    <label for="langJs">JavaScript</label>
                </div>
                <div class="select">
                    <label for="biografia">Biografia</label>
                    <br>
                    <input type="text" id="biografia" v-model="usuario.bio" required>
                </div>
                <div class="botao">
                    <button class="botao" type="submit">Enviar</button>
                </div>
            </form>
        </main>
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

input {
    background-color: cornflowerblue;
    border: 1px solid black;
    margin-left: 10px;
    margin-top: 10px;
    min-width: 300px;
    min-height: 35px;
    border-radius: 10px;
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
    margin-top: 10px;
    margin-bottom: 10px;
    border: 2px solid black;
    background-color: blue;
    color: aliceblue;
}

.form-enter-active,
.form-leave-active {
    transition: opacidade 0.5s ease;
}
</style>