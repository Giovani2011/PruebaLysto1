<template>
  <div class="q-pa-md">
    <div class="contenedor">
      <div class="contenedorint" style="max-width: 500px">
        <q-input v-model="text" label="Buscar animal" />
        <q-btn @click="obtenerDatos" label="Buscar" />
      </div>
    </div>
    <h2 class="t1">Resultados</h2>
    <br />
    <div v-if="resultado" class="card-container">
      <div class="card" v-for="photo in resultado.photos" :key="photo.id">
        <img :src="photo.src.medium" :alt="photo.alt" />
      </div>
    </div>
    <div v-if="error">
      <p>Error al obtener datos: {{ error }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      text: '', // Variable para almacenar el texto del input
      resultado: null, // Variable para almacenar el resultado de la API
      error: null // Variable para almacenar errores
    };
  },
  methods: {
    async obtenerDatos() {
      this.error = null; // Reinicia el error antes de la nueva solicitud
      try {
        // Realiza la petición GET a la API
        const response = await axios.get(`https://api.pexels.com/v1/search?query=${this.text}`, {
          headers: {
            Authorization: 'kM9Q4hYzKIgx6Va2cMDGV0O5inQdKK20ArWmUpsemGyPFGiUYWNw7yXe' // Reemplaza con tu clave de API
          }
        });
        this.resultado = response.data; // Almacena el resultado en la variable
      } catch (error) {
        console.error('Error al obtener datos:', error);
        this.error = 'Error al obtener datos'; // Almacena el mensaje de error
        this.resultado = null; // Reinicia el resultado en caso de error
      }
    }
  }
};
</script>

<style scoped>
.contenedor {
  display: flex;
  justify-content: center;
}
.contenedorint {
  display: flex;
  flex-direction: column;
  gap: 5px;
}
.t1 {
  font-size: 3.5rem;
  text-align: center;
}
.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 10px; /* Espacio entre las tarjetas */
}
.card {
  border-radius: 8px;
  overflow: hidden;
}
.card img {
  width: 100%; /* Imagen ocupa todo el ancho de la tarjeta */
  height: auto; /* Mantiene la proporción de la imagen */
}
</style>
