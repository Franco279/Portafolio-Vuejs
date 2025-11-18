<script setup>
import { ref } from 'vue';

// ✅ Colores simplificados a un array de strings
const fechaColor = ref([
    '#41516c',
    '#FBCA3E',
    '#E24A68',
    '#1B5F8C',
    '#4CADAD'
]);

const educacion = ref([
    { fecha: '2024', title: 'Desarrollador Full-Stack & Apps', descripcion: 'Lideré el desarrollo de un portal de servicios al cliente. Trabajé con Vue.js 3 (Composition API) y Node.js (Express) para construir APIs RESTful y un panel de administración.' },
    { fecha: '2023', title: 'Especialización en Desarrollo Web y Lógica de Juego', descripcion: 'Enfocado en la interactividad y la lógica de sistemas. Construí una plataforma de e-learning utilizando Python (Django) en el back-end y Vanilla JavaScript en el front-end, implementando lógica compleja de seguimiento de progreso.' },
    { fecha: '2022', title: 'Iniciación y Consolidación de Habilidades Web', descripcion: 'Transición de conocimientos universitarios a un entorno profesional. Desarrollé una pequeña aplicación web educativa utilizando la librería Phaser.js para crear un juego simple basado en navegador, aplicando mis conocimientos de la UTN en programación orientada a objetos (POO).' },
    { fecha: '2021', title: 'Formación, Prácticas y Estudios', descripcion: 'Enfoque en fundamentos y primeros proyectos. Creé mi primer portafolio web estático utilizando HTML/CSS puros para mostrar mis ejercicios de programación iniciales.' }
]);

// ✅ Función getColor corregida para el nuevo array de colores
const getColor = (index) => {
    return fechaColor.value[index % fechaColor.value.length];
};
</script>

<template>
<div class="timeline-container">
    <div 
        v-for="(item, index) in educacion" 
        :key="index" 
        class="timeline-item"
    >
        <div class="timeline-point" :style="{ backgroundColor: getColor(index) }">
            </div>
        
        <div class="timeline-content">
            <span class="timeline-date">{{ item.fecha }}</span>
            <h3>{{ item.title }}</h3>
            <p>{{ item.descripcion }}</p>
        </div>
    </div>
</div>
</template>

---

## 🎨 Estilos Básicos para la Línea de Tiempo

Para que esto realmente se vea como una línea de tiempo, necesitas aplicar los siguientes estilos básicos. Tendrás que ajustar los colores, márgenes y alineaciones a tu diseño general, pero esto crea la estructura vertical. 

[Image of timeline web design]


```vue
<style scoped>
/* Contenedor Principal */
.timeline-container {
    max-width: 800px;
    margin: 40px auto;
    position: relative;
    padding: 20px 0;
}

/* Línea Vertical Central */
.timeline-container::before {
    content: '';
    position: absolute;
    top: 0;
    left: 50%; /* Centra la línea */
    width: 2px;
    height: 100%;
    background-color: #bbd5f1; /* Color de la línea */
    transform: translateX(-50%);
}

/* Item de la Línea de Tiempo */
.timeline-item {
    display: flex;
    justify-content: flex-end; /* Por defecto, coloca el contenido a la derecha */
    margin-bottom: 40px;
    position: relative;
    width: 50%; /* Cada item ocupa la mitad del ancho */
}

/* Ajuste para que el contenido se alterne (izquierda/derecha) */
.timeline-item:nth-child(even) {
    justify-content: flex-start; /* Contenido a la izquierda */
    margin-left: 50%;
}

/* Punto o Círculo */
.timeline-point {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    position: absolute;
    top: 5px; /* Ajusta la posición vertical del punto */
    z-index: 10;
    box-shadow: 0 0 0 4px rgba(255, 255, 255, 0.5);
    transform: translateX(-50%); /* Ajuste fino para centrar en la línea */
}

/* Posicionamiento de los Puntos */
.timeline-item:nth-child(odd) .timeline-point {
    left: 100%; /* Puntos a la derecha para items impares */
}
.timeline-item:nth-child(even) .timeline-point {
    right: 100%; /* Puntos a la izquierda para items pares */
    left: auto;
}

/* Contenido del Evento */
.timeline-content {
    background-color: #293d7c; /* Color de fondo de la tarjeta */
    padding: 15px;
    border-radius: 6px;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.2);
    width: 90%;
    color: #EAF2FA;
    text-align: left;
}

.timeline-date {
    display: block;
    font-weight: bold;
    color: #FBCA3E;
    margin-bottom: 5px;
}

@media (max-width: 768px) {
    /* Diseño responsivo: todo a la derecha en pantallas pequeñas */
    .timeline-container::before {
        left: 20px;
    }
    .timeline-item, .timeline-item:nth-child(even) {
        width: 100%;
        margin-left: 0;
        justify-content: flex-start;
        padding-left: 40px;
    }
    .timeline-point, .timeline-item:nth-child(even) .timeline-point {
        left: 20px;
        transform: translateX(-50%);
    }
}
</style>