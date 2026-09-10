<script setup>
  import { ref } from 'vue'
  const esperando = ref(false)
  const caracteristicas = defineProps(['urlImg', 'titulo', 'descripcion', 'autor'])
  

</script>
<template>
  <v-card
    class="mx-auto   w-11/12"
    max-width="1000"
  >
    <v-img
      class="align-end text-white"
      cover
      height="200"
      :src="urlImg"
    >
      <v-card-title>{{ caracteristicas.titulo }}</v-card-title>
    </v-img>
    <v-progress-linear
      v-show="esperando"
      color="primary"
      indeterminate
      model-value="20"
      :height="5"
    ></v-progress-linear>
    <v-card-subtitle class="pt-4">
      {{ caracteristicas.autor }}
    </v-card-subtitle>
    <v-card-text>
      <div>{{ caracteristicas.descripcion }}</div>

    </v-card-text>

    <v-card-actions>
      <v-btn color="orange" text="Share"></v-btn>

      <v-btn color="orange" text="Explore"></v-btn>
    </v-card-actions>
  </v-card>
</template>