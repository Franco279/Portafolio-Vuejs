<script setup>
// Rutas absolutas a relativas
import icono1 from '../icons/trabajo1.svg';
import icono2 from '../icons/trabajo2.svg';
import icono3 from '../icons/trabajo3.svg'; // ✅ Nota la corrección de 'c trabajo3' a 'trabajo3'
import icono4 from '../icons/trabajo4.svg';

import { ref } from 'vue';
const titulo = 'Desarrollador Full Stack';
const fecha = 'Desde Enero 2021 / Diciembre 2024';
const experiencias = ref([
    { id: 1, src: icono1, parrafo: 'Como líder técnico, encabecé la creación de una plataforma de comercio electrónico de alto rendimiento..' },
    { id: 2, src: icono2, parrafo: 'Identifiqué y resolví los cuellos de botella de rendimiento en la aplicación. Al optimizar las consultas en Node.js y refinar la carga de componentes en React, conseguí reducir el tiempo de carga de las páginas en un 50%.' },
    { id: 3, src: icono3, parrafo: 'Durante el proyecto de migración, fui el encargado de diseñar e implementar las soluciones robustas de autenticación y autorización.' },
    { id: 4, src: icono4, parrafo: 'Implementé una tubería de Despliegue Continuo (CI/CD) completa utilizando Jenkins y Docker.' }
]);
</script>

<template>
    <div class="card">
        <h3 class="titulo">{{ titulo.toLocaleUpperCase() }}</h3>
        <p class="fecha">{{ fecha }}</p>
        <ul class="listado">
            <li class="item" v-for="experencia in experiencias" :key="experencia.id">
                <img class="imagen-svg" :src="experencia.src" width="45rem" alt="Icono de habilidad o tarea de experiencia">
                <p>{{ experencia.parrafo }}</p>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    padding: 2rem;
    background-color: rgb(28, 41, 52);
    border-radius: 15px;
}

.titulo {
    font-size: 1.5rem;
    color: coral;
}

.fecha {
    font-size: 1rem;
    color: burlywood;
    margin-bottom: 1rem;
}

.listado {
    display: flex;
    flex-direction: column;
    /* ✅ Adiciones de CSS para limpieza de listas */
    list-style: none;
    padding: 0;
    margin: 0;
}

.item {
    align-items: center;
    display: flex;
    padding: 1rem;
    gap: 1.5rem;
}
</style>