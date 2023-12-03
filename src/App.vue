<script setup>
import Api from './components/Api.vue';
import Eval from './components/Eval.vue';
import EvalIng from './components/EvalIng.vue';
import Datos from './components/Datos.vue';
</script>

<template>
  <div>
    <header>
      <Api></Api>
    </header>
    <body>
      <Eval></Eval>
      <div class="espacio"></div>
      <Datos></Datos>
      <div class="espacio"></div>
      <EvalIng></EvalIng>
      <div class="espacio"></div>
    </body>
  </div>
</template>

<style>
  /* Estilo para agregar espacio hacia abajo */
  .espacio {
    background-color: rgb(229, 152, 102); /* Cambia el color según tus preferencias */
    height: 40px; /* Ajusta el valor según tus necesidades */
  }
</style>

