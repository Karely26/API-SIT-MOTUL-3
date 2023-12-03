<script setup>
import { onMounted } from 'vue';
import { ref } from 'vue';

const info = ref('');

async function fetchData() {
    try {
        const response = await fetch('https://sitmotul.com.mx/api/statusEval')
        const data = await response.json();
        info.value = data
        console.log(info.value);
    } catch (error) {
        console.error('Error al obtener datos:', error);
    }
}
onMounted(() => {
    fetchData();
})
</script>

<template>
  <body class="fond">
    <header class="w-full">
      <div class="w-full flex flex-col gap-y-3">
        <div class="w-full flex flex-col gap-y-1 place-items-center px-4  md:px-8 lg:px-16">
          <img alt="Sit logo" class="logo" src="@/components/icons/logoS.svg" width="200" height="200" />
          <h1 class="title">SITMOTUL</h1>
          <h3 class="text">Información sobre la evaluación al tutor del ciclo escolar {{ info.periodo }}</h3>
        </div>
      </div>
    </header>
  </body>
  
  
</template>
<style scoped>
    /* Estilos generales que se aplicarán en todas las pantallas */
    .fond {
      background-color: rgb(175, 96, 26);
    }

    .title {
      font-size: 25px;
    }

    .text {
      font-size: 20px;
    }

    .bolded {
      font-weight: bold; 
      font-size: 20px;
      text-decoration: underline;
    }

    .bolded2 {
      font-weight: bold; 
      font-size: 20px;
    }

    header {
      line-height: 1.5;
      max-height: 100vh;
    }

    .logo {
      display: block;
      margin: 0 auto 2rem;
    }

    @media only screen and (max-width: 600px) {
      /* Estilos específicos para pantallas más pequeñas */
      .fond {
        background-color: rgb(175, 96, 26);
      }

      /* Otros estilos para móviles */
    }
  </style>