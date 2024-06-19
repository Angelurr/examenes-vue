<script setup>
import { ref } from 'vue';

const registros = ref([
    {
        Fecha: "10 de junio 2024",
        Peso: 80,
        Cintura: 78,
        Cadera: 86
    },
    {
        Fecha: "12 de julio 2024",
        Peso: 78,
        Cintura: 76,
        Cadera: 84
    },
    {
        Fecha: "9 de agosto 2024",
        Peso: 76,
        Cintura: 74,
        Cadera: 82
    }
]);

const nuevaFecha = ref('');
const nuevoPeso = ref('');
const nuevaCintura = ref('');
const nuevaCadera = ref('');

function añadirRegistro() {
    registros.value.push({
        Fecha: nuevaFecha.value,
        Peso: parseInt(nuevoPeso.value),
        Cintura: parseInt(nuevaCintura.value),
        Cadera: parseInt(nuevaCadera.value)
    });

    nuevaFecha.value = '';
    nuevoPeso.value = '';
    nuevaCintura.value = '';
    nuevaCadera.value = '';
}

function calcularPesoPerdido() {
    if (registros.value.length > 1) {
        return registros.value[0].Peso - registros.value[registros.value.length - 1].Peso;
    }
    return 0;
}

function calcularReduccionCintura() {
    if (registros.value.length > 1) {
        return registros.value[0].Cintura - registros.value[registros.value.length - 1].Cintura;
    }
    return 0;
}

function calcularReduccionCadera() {
    if (registros.value.length > 1) {
        return registros.value[0].Cadera - registros.value[registros.value.length - 1].Cadera;
    }
    return 0;
}
</script>

<template>
    <div v-for="(registro, i) in registros" :key="i" class="bg-green-400 w-60 h-36 mt-4 mx-auto">
        <div class="pt-5 ml-3 font-semibold">
            <p>{{ registro.Fecha }}</p>
            <p>Peso: {{ registro.Peso }}kg</p>
            <p>Cintura: {{ registro.Cintura }}cm</p>
            <p>Cadera: {{ registro.Cadera }}cm</p>
        </div>
    </div>
    <div class="flex justify-center mt-4">
        <div class="mr-16">
            <h2>Peso Perdido: {{ calcularPesoPerdido() }}kg</h2>
        </div>
        <div class="mr-16">
            <h2>Reducción Cintura: {{ calcularReduccionCintura() }}cm</h2>
        </div>
        <div>
            <h2>Reducción Cadera: {{ calcularReduccionCadera() }}cm</h2>
        </div>
    </div>

    <div class="bg-green-400 h-44 w-60 mx-auto mt-16">
        <div class="pt-4">
            <input v-model="nuevaFecha" class="ml-3 mt-1 w-52 rounded-sm" type="text" placeholder="Fecha">
            <input v-model="nuevoPeso" class="ml-3 mt-1 w-52 rounded-sm" type="text" placeholder="Peso">
            <input v-model="nuevaCintura" class="ml-3 mt-1 w-52 rounded-sm" type="text" placeholder="Talla cintura">
            <input v-model="nuevaCadera" class="ml-3 mt-1 w-52 rounded-sm" type="text" placeholder="Talla cadera">
        </div>
        <div class="flex justify-end mr-4 mt-4">
            <div @click="añadirRegistro" class="bg-slate-200 w-20 h-6 rounded-sm cursor-pointer">
                <p class="ml-4">Añadir</p>
            </div>
        </div>
    </div>
</template>