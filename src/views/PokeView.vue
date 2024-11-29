<script setup>
import axios from "axios";
import { useRoute, useRouter } from 'vue-router';
import { ref } from "vue";
import { useGetData } from "@/composables/getData";

const { data, getData, loading, error } = useGetData();

const route = useRoute();
const router = useRouter();

const back = () => {
    router.push("/pokemons")
}

const poke = ref({});

</script>
getData(`https://pokeapi.co/api/v2/pokemon/${route.params.name}`);


<template>
    <p v-if="loading">Cargando información...</p>
    <div class="alert alert-danger mt-2" v-if="error"> {{ error }}</div>
    <div v-if="data">
        <img :src="data.sprites?.front_default" alt="">
        <h1>Poke name: {{ $route.params.name }}</h1>
    </div>
    <button @click="back" class="btn btn-outline-primary">Volver</button>
</template>