<template>
  <div class="juegos wrapper">
    <h1 class="juegos__title">Tienda 32 Bits</h1>
   
      <h3 class="juegos__subtitle">Lista de juegos</h3>
  
      <table class="juegos__table">
        <thead>
          <tr>
            <th>Código</th>
            <th>Nombre</th>
            <th>Stock</th>
            <th>Precio</th>
            <th>Acciones</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="juego of juegos" :key="juego.codigo" >
            <td>{{ juego.codigo }}</td>
            <td>{{ juego.nombre }}</td>
            <td>{{ juego.stock }}</td>
            <td>{{ juego.precio }}</td>
            <td>
              <button @click="changeStock({ codigo: juego.codigo, action: 'restar' })" >-</button>
              <button @click="changeStock({ codigo: juego.codigo, action: 'sumar' })">+</button>
            </td>
          </tr>
        </tbody>
      </table>


  </div>
</template>

<script>
import { mapActions, mapState } from 'vuex';

export default {
  computed: {
    ...mapState(["juegos"]),
  },
  methods: {
    ...mapActions(["changeStock"])
  },
}


</script>

<style>

  .juegos {
    text-align: center;
    margin: 0 auto;
    padding: 3rem;
    max-width: 55rem;
    background-color: burlywood;
    border-radius: 1rem;
    box-shadow: 0 0 1rem black;
  }

  table,
  th,
  td {
    border: 2px solid black;
  }

  td,
  th {
    padding: 0 3rem;
    text-align: center;
    border-radius: 1rem;
  }

  .juegos__table {
    margin: 0 auto;
    background-color: bisque;
  }

  .juegos__title {
    text-align: center;
    font-size: 3rem;
    box-shadow: 0 0 1rem black;
    border-radius: 1rem;
  }

  .juegos__subtitle {
    text-align: center;
    font-size: 2rem;
    box-shadow: 0 0 1rem black;
    border-radius: 0.5rem;
  }

  button {
    background-color: rgb(235, 187, 187);
    border: 1px solid black;
    border-radius: 5px;
  }

</style>