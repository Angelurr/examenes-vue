<script setup>
import { ref } from 'vue';

const registros = ref([
    {
        icon: 'https://br.web.img3.acsta.net/pictures/19/05/22/10/42/3773139.jpg',
        nombre: "Michael Deo",
        hijo: [
            { datos: "asdasddas" },
            { datos: "asdasddasasdasdasd" },
            { datos: "asdasddas" }
        ],
    },
    {
        icon: 'https://br.web.img3.acsta.net/pictures/19/05/22/10/42/3773139.jpg',
        nombre: "Miguel Angel",
        hijo: [
            { datos: "asdasddas" },
            { datos: "asdasddasasdasdasd" },
            { datos: "asdasddas" }
        ]
    },
    {
        icon: 'https://br.web.img3.acsta.net/pictures/19/05/22/10/42/3773139.jpg',
        nombre: "John Doe",
        hijo: [
            { datos: "data1" },
            { datos: "data2" },
            { datos: "data3" }
        ]
    },
    {
        icon: 'https://br.web.img3.acsta.net/pictures/19/05/22/10/42/3773139.jpg',
        nombre: "Jane Smith",
        hijo: [
            { datos: "dataA" },
            { datos: "dataB" },
            { datos: "dataC" }
        ]
    },
    {
        nombre: "Emily White",
        hijo: [
            { datos: "dataX" },
            { datos: "dataY" },
            { datos: "dataZ" }
        ]
    },
    {
        nombre: "James Brown",
        hijo: [
            { datos: "dataL" },
            { datos: "dataM" },
            { datos: "dataN" }
        ]
    },
    {
        nombre: "Maria Garcia",
        hijo: [
            { datos: "dataP" },
            { datos: "dataQ" },
            { datos: "dataR" }
        ]
    },
    {
        nombre: "Carlos Perez",
        hijo: [
            { datos: "dataT" },
            { datos: "dataU" },
            { datos: "dataV" }
        ]
    },
]);

let indice = ref(0);
let mostrarRegistros = ref(registros.value.slice(indice.value, indice.value + 4));

function actualizarVista() {
  mostrarRegistros.value = registros.value.slice(indice.value, indice.value + 4);
}

// Función para mostrar el siguiente grupo de 4 personas
function siguiente() {
  if (indice.value + 4 < registros.value.length) {
    indice.value += 4;
    actualizarVista();
  }
}

// Función para mostrar el grupo anterior de 4 personas
function anterior() {
  if (indice.value - 4 >= 0) {
    indice.value -= 4;
    actualizarVista();
  }
}

</script>

<template>
    <div class="bg-slate-300 w-[25rem] h-[50rem] mx-auto mt-5">
        <div class="pt-2 ml-6">
            <div class="mt-4 mr-5 bg-slate-100 p-4" v-for="(registro, i) in mostrarRegistros" :key="i">
                <div class="flex items-center">
                    <div v-if="registro.icon" :style="{ backgroundImage: `url(${registro.icon})` }" class="w-20 h-20 bg-cover bg-center rounded-full"></div>
                    <div class="ml-4 ">
                        <div>{{ registro.nombre }}</div>
                        <div class="text-sm" v-for="(dato, j) in registro.hijo" :key="j">{{ dato.datos }}</div>
                        <div class="flex gap-1 mt-2">
                            <p class="bg-blue-600 text-white px-2 py-1 rounded">Follow</p>
                            <p class="bg-blue-600 text-white px-2 py-1 rounded">Mensaje</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="flex justify-between mt-4 px-4">
            <p @click="anterior" class="cursor-pointer">Anterior</p>
            <p @click="siguiente" class="cursor-pointer">Siguiente</p>
        </div>
    </div>
</template>
