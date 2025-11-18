<script setup>
import NavBar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import Educacion from './components/Educacion.vue';
import ExperienciaComponente from './components/ExperienciaComponente.vue'; 
import Proyectos from './components/ProyectosComponente.vue'; 
import HabilidadesComponente from './components/HabilidadesComponente.vue';
import InteresesComponente from './components/InteresesComponente.vue'; 
</script>

<template>
  <header>
    <NavBar/>
  </header>
  
  <main>
    <DatosPersonales />

    <section id="educacion">
      <h2>Educación - Cursos</h2>
      <Educacion/>
    </section>
    
    <section id="experiencia">
      <h2>Experiencia</h2>
      <ExperienciaComponente/>
    </section>
    
    <section id="proyectos">
      <h2>Proyectos</h2>
      <Proyectos/> 
    </section>

    <section id="habilidades">
      <h2>Habilidades</h2>
      <HabilidadesComponente/>
    </section>
    <section id="intereses">
      <h2>Intereses</h2>
      <InteresesComponente/>
    </section>
  </main>
</template>

<style>
html, body {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
  overflow-x: hidden; 
}

body {
  background: linear-gradient(-45deg, #E0E6ED, #1A1F71, #6C63FF, #3E5C76);
  background-size: 600% 600%; 
  animation: gradientBG 10s ease infinite; 
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  color: rgb(184, 223, 255);
}

@keyframes gradientBG {
  0% { background-position: 0% 50%; }
  25% { background-position: 50% 100%; }
  50% { background-position: 100% 50%; }
  75% { background-position: 50% 0%; }
  100% { background-position: 0% 50%; }
}

/* Footer y títulos visibles */
footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
  font-size: 1.3rem;
}
h2 {
  color: rgb(180, 194, 220); 
}

</style>