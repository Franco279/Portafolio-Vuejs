<script setup>
import instagramIcon from '../icons/insta.svg'; 
import githubIcon from '../icons/github.svg';

const title = 'Franco Cala';
const descripcion = 'ecnico Universitario en Programación - Tutorial UTN';
const residencia = 'San Rafael, Mendoza, Argentina';
const presentacion = 'Bienvenidos a mi portafolio de proyectos, soy un desarrollador web con experiencias en el desarrollo de videojuegos y app';
const redesSociaes = [
    {id: 1, name: 'Instagram', src: instagramIcon, url: 'https://www.instagram.com/franco.cala.7/'},
    {id: 2, name: 'github', src: githubIcon, url: 'https://github.com/Franco279'},
];
const telefono = '+5492604355077';
</script>

<template>
    <section class="datos-personales">
        <div class="card">
            <h1>{{ title }}</h1>
            <h2>T{{ descripcion }}</h2>
            <p>{{ presentacion }}</p>
            <ul class="container-lista">
    <li v-for="red in redesSociaes" :key="red.id">
        <a :href="red.url" target="_blank">
            <img class="icon-redsocial" :src="red.src" width="35rem" :alt="'Icono de ' + red.name">
            {{ red.name }}
        </a>
    </li>
</ul>
                <h3>Mi Telefono pesonal: {{ telefono }}</h3>
                <h4>{{residencia}}</h4>
        </div>
    </section>
</template>

<style scoped>
h1 {
    font-size: 2.5rem;
    color: #bbd5f1; 
}

p {
    font-size: 1.2rem;
    font-weight: 600;
    margin-bottom: 1rem;
    color: #5DA9E9;
}

.card{
    background-color: #293d7c;
    border-radius: 10px;
    padding: 10px;
    margin: 10px;
    text-align: center;
    color: #EAF2FA;
}

.container-lista {
    display: flex;
    justify-content: center;
    list-style: none;
    /* ✅ Usar 0 en lugar de 0% */
    padding: 0; 
    margin: 0;
    text-align: center;
}

/* Estilos base para el enlace (Mejora UX) */
.container-lista a {
    display: flex; /* Para alinear el icono y el texto */
    align-items: center;
    text-decoration: none;
    color: inherit;
}

.icon-redsocial {
    background-color: #EAF2FA;
    border-radius: 50%;
    padding: 2px;
    margin: 5px;
    box-shadow: 0 0 5px rgba(58, 124, 165, 0.6);
    /* Se quitó el :hover de aquí */
}

/* ✅ CORRECCIÓN: El hover se aplica al enlace (a) y modifica el icono dentro */
.container-lista a:hover .icon-redsocial {
    background-color: #1B3B5F;
    box-shadow: 0 0 5px rgba(251, 249, 249, 0.934);
}

/* Efecto de hover adicional en el texto del enlace */
.container-lista a:hover {
    color: #bbd5f1; 
}

h2{
    font-size: 1.2rem;
    font-weight: 600;
    color: #EAF2FA;
}

</style>