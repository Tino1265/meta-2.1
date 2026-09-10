<template>
    <AppBar/>
  <v-container fluid class=" flex flex-col md:flex-row gap-5   w-full  justify-between  mt-10 pt-8 px-4">
    <TarjetaConImagen 
      :urlImg="url1" 
      titulo="Ciudades interesantes" 
      descripcion="descripciones" 
      :autor="autor1" 
    />
    <TarjetaConImagen 
      :urlImg="url2" 
      titulo="Ciudades interesantes" 
      descripcion="descripciones" 
      :autor="autor2" 
    />
  </v-container>
  <v-container class="max-w-md mx-auto">
    <v-alert
      v-model="error"
      title="Error de conexión"
      text="No se pudieron cargar las imágenes de la API. Inténtalo de nuevo."
      closable
      class="my-1 bg-red-600 text-white"
    ></v-alert>
  </v-container>
  <div class="flex justify-center m-10">
    <v-btn :loading="cargando" :disabled="cargando" @click="ObtenerImagenes">
        Cambiar
    </v-btn>
  </div>
  <div class=" max-w-7xl w-full my-3 mx-auto">
    <Table/>
  </div>
  <Footer/>
</template>

<script setup>
import AppBar from '@/components/AppBar.vue';
import Footer from '@/components/Footer.vue';
import Table from '@/components/Table.vue';
import TarjetaConImagen from '@/components/TarjetaConImagen.vue';
import { ref } from 'vue';
const url1 = ref('')
const url2 = ref('')
const autor1 = ref('')
const autor2 = ref('')
const cargando = ref(false)
const error = ref(false);
const ObtenerImagenes = async ()=>{

    cargando.value = true
    try{
      const imgs = await fetch("https://picsum.photos/v2/list?page=1&limit=50");
      const imgsArray = await imgs.json()
      obtenerUrls(imgsArray)
      error.value = false
    }catch(e){
       error.value = true
       cargando.value = false
    }
}
const obtenerUrls = (x)=>{
    let num1 = 0
    let num2 = 0
    do {
        num1 = Math.floor(Math.random() * 50)
        num2 = Math.floor(Math.random() * 50)
    }while(num1 == num2)
    url1.value = x[num1].download_url
    url2.value = x[num2].download_url
    autor1.value = x[num1].author
    autor2.value = x[num2].author
    cargando.value = false
}
</script>