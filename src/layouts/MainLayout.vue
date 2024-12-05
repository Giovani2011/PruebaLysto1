<template>
  <div>
    <h1 class="t1">Aplicación axios solo GET</h1>
    <axios-component />
  </div>
</template>

<script>
import AxiosComponent from '../components/Busqueda.vue'; // Asegúrate de que la ruta sea correcta

export default {
  components: {
    AxiosComponent
  }
};

</script>

<style>

.contenedor{
  display: flex;
  justify-content: center;
}
.contenedorint{
  display: flex;
  flex-direction: column;
  gap: 5px;
}


.t1{
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
<style>

.contenedor{
  display: flex;
  justify-content: center;
}
.contenedorint{
  display: flex;
  flex-direction: column;
  gap: 5px;
}


.t1{
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
