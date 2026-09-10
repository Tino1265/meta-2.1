<template>
  <v-table theme="dark">
    <thead>
      <tr>
        <th class="text-left">
          Categoria
        </th>
        <th class="text-left">
          Valor
        </th>
        <th class="text-left">
          Estado
        </th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Matricula</td> 
        <td>1190622</td>
        <td>Activo</td>
    </tr>
    <tr>
        <td>Carrera</td> 
        <td>Ingenieria en computacion</td>
        <td>activo</td>
    </tr>
    <tr>
        <td>Promedio</td> 
        <td>9.0</td>
        <td>General</td>
    </tr>
    <tr>
        <td>Correo</td> 
        <td>juventino.ramos@uabc.edu.mx</td>
        <td>Verificado</td>
    </tr>
    </tbody>
  </v-table>
</template>
<script setup>
  import { ref } from 'vue'

  const desserts = ref([
    {
      name: 'Frozen Yogurt',
      calories: 159,
    },
    {
      name: 'Ice cream sandwich',
      calories: 237,
    },
    {
      name: 'Eclair',
      calories: 262,
    },
    {
      name: 'Cupcake',
      calories: 305,
    },
    {
      name: 'Gingerbread',
      calories: 356,
    },
    {
      name: 'Jelly bean',
      calories: 375,
    },
    {
      name: 'Lollipop',
      calories: 392,
    },
    {
      name: 'Honeycomb',
      calories: 408,
    },
    {
      name: 'Donut',
      calories: 452,
    },
    {
      name: 'KitKat',
      calories: 518,
    },
  ])
</script>