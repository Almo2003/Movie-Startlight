<template>
    <div class="filters-container">
          <ion-button class="secundary" @click="filterByCategory('now_playing')">Cartelera</ion-button>
          <ion-button class="secundary" @click="filterByCategory('top_rated')">Mejor Calificadas</ion-button>
          <ion-button class="secundary" @click="filterByCategory('popular')">Populares</ion-button>
    </div>
  </template> 
  <script lang="ts">
  import { defineComponent } from 'vue';
  import { IonButton } from '@ionic/vue';
  
  export default defineComponent({
    components: {
      IonButton
    },
    emits: ['filter-category'],
    methods: {
      filterByCategory(category: string) {
        this.$emit('filter-category', category);
      }
    }
  });
  </script>
  
  <style scoped>
  .filters-container {
    display: flex;
    justify-content: center; /* Centra los botones horizontalmente */
    gap: 1rem; /* Espacio entre los botones */
    padding: 1rem; /* Ajusta el padding para separar del borde */
    margin-top: 2rem; 
    flex-wrap: wrap; /* Permite que los botones se envuelvan cuando no caben en una sola línea */
    background-color: orange; /* Fondo oscuro para resaltar los botones */
    border-radius: 8px; /* Bordes redondeados para una apariencia más suave */
  }
  
  
  ion-button{
    max-width: 150px; 
    flex: 1 1 auto; /* Flex-grow, flex-shrink, flex-basis */
    margin: 0.5rem; /* Margen entre los botones */
    color: white; /* Color del texto */
    background-color: black;
    background: #000;
    --border-radius: 20px; /* Bordes redondeados del botón */
    --padding-start: 1.75rem; /* Padding izquierdo */
    --padding-end: 1.75rem; /* Padding derecho */

  }
  .button-solid {
    --background: #000;
    --color: var(--ion-color-primary-contrast, #fff);
    border-radius: 50%;
  }
  .button-solid:hover{
    box-shadow: 0 4px 15px rgb(249, 252, 249);
  }
  
  </style>
  