<script setup>
import { ref } from 'vue';
import formL from '@/components/formL.vue';
import infoForm from '@/components/infoForm.vue';

const mostrarInfo = ref(false);

const dadosUsuario = ref({})

function enviar(usuario) {
  dadosUsuario.value = usuario;
  mostrarInfo.value = true;
}

function voltar() {
  mostrarInfo.value = false;
}


</script>

<template>
  <formL v-if="!mostrarInfo" :dados="dadosUsuario" @submit="enviar" />
  <infoForm v-if="mostrarInfo" :usuario="dadosUsuario" @voltar="voltar" />

</template>

<style scoped></style>