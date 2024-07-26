<script setup>
import { ref } from "vue";
export default {
  props: {
    usuario: Object
  }
}
</script>

<template>
    <div>
        <h2>Informações do usuario</h2>
        <p>{{ usuario.nome }}</p>
        <p>{{ usuario.email }}</p>
        <p></p>
        <p></p>
        <p></p>
        <p></p>
        <p></p>
        <p></p>
        <p></p>
    </div>
</template>

<style scoped>

</style>