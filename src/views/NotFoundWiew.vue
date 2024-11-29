<script setup>
import { useRouter } from 'vue-router';

const router = useRouter();

const back = () => {
    router.push("/")
}
</script>


<template>
    <h1>404 Pagina no Disponible!</h1>
    <button @click="back">Volver</button>
</template>