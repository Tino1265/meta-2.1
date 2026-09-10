<template>
    <v-footer class=" bg-slate-900 text-white font-bol text-xs mt-auto">
    <v-container  fluid>
        <v-row align="center" justify=" space-between">
            <v-col cols="12" sm="6" md="4" class="text-center text-sm-start">
                <div class="text-subtitle-1 font-weight-bold">Datos del Estudiante</div>
                <div class="text-body-2">Nombre: Juventino Alexis Ramos Aguilera</div>
                <div class="text-body-2">Matrícula: 1190622</div>
            </v-col>
            <v-col cols="12" sm="6" md="4" class="text-center">
                <div class="text-subtitle-1 font-weight-bold">Fecha Actual</div>
                <div class="text-body-2">{{ fechaActual }}</div>
            </v-col>
            <v-col cols="12" md="4" class="text-center text-md-end">
                <div class="text-subtitle-1 font-weight-bold">Contacto</div>
                <div class="text-body-2">correo@estudiante.edu</div>
                <div class="text-caption text-grey-lighten-1 mt-1">
                    © {{ anioActual }} Todos los derechos reservados
                </div>
            </v-col>
        </v-row>
    </v-container>
  </v-footer>
</template>
<script setup>
import { ref } from 'vue';

const fechaActual = ref('')
const hoy = new Date()
  const opciones = { year: 'numeric', month: 'long', day: 'numeric' }
  fechaActual.value = hoy.toLocaleDateString('es-ES', opciones)
</script>