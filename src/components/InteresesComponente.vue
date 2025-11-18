<script setup>
import { ref } from 'vue';
import FondoLava from './FondoLava.vue'; // Asegúrate que esta ruta es correcta

const intereses = ref([
    'La Innovación Constante: Estoy en aprendizaje continuo de nuevas librerías y patrones de diseño (como Node.js, Git y bases de datos como MySQL), integrando estas herramientas para construir soluciones full-stack robustas.',
    'El Diseño y la Usabilidad (UX/UI): Mi enfoque no termina cuando el código compila; busco que cada interfaz sea no solo funcional, sino también placentera y accesible.',
    'El Crecimiento Personal y Profesional: El idioma inglés (Nivel C1) y las diversas herramientas de software me permiten mantenerme al día con las tendencias globales de la tecnología y colaborar en entornos internacionales.',
]);
</script>

<template>
    <div class="intereses-contenedor">
        <FondoLava />
        <ul class="contenedor-lista">
            <li class="item" v-for="(interes, index) in intereses" :key="index">
                {{ interes }}
            </li>
        </ul>
    </div>
</template>

<style scoped>
/* Estilos CLAVE: Posicionamiento para que el contenido flote sobre el fondo */
.intereses-contenedor {
    position: relative; /* CLAVE: Contiene el FondoLava absoluto */
    padding: 40px 30px; 
    border-radius: 12px;
    /* El background del contenedor ya no es necesario, lo pone el SVG */
    background: transparent; 
    overflow: hidden; /* Oculta partes del SVG que se salgan del borde */
}

.contenedor-lista {
    /* CLAVE: Asegura la visibilidad por encima del FondoLava */
    position: relative; 
    z-index: 2; /* Mayor que el z-index del FondoLava */
    list-style-type: none;
    padding: 0;
    margin: 0;
    color: #2c3e50; 
}

.item {
    margin-bottom: 20px;
    padding: 10px 15px;
    border-left: 4px solid #9b5de5; /* Color que hace juego con el SVG */
    background-color: rgba(255, 255, 255, 0.85); /* Fondo semitransparente para legibilidad */
    border-radius: 4px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}
</style>