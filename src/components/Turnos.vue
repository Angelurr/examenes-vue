<!-- <script setup>
import { ref } from 'vue';

const datos = ref([
    "XDCHH",
    "HT550",
    "G3WQ",
    "PTWE"

]);

function suma(){

}








</script>

<template>
    <div class="w-[49rem] h-[30rem] bg-slate-100 mx-auto mt-20 shadow-2xl shadow-gray-600 border border-gray-500 ">
        <div class="pt-12" >
            <h1 class=" text-center font-bold ">SISTEMA DE TURNOS</h1>
        </div>
       <div class="flex justify-evenly mt-3">
          <div class="w-56 h-48 bg-slate-300 ml-10" >
              <div class="bg-cyan-500 h-9">
                <h2 class=" pt-1 text-center text-white font-semibold">MODULO 1</h2>
              </div>
              <div class="">
                <p v-for="(dato, i) in datos":key="i" class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">{{ i+1 }}-{{ dato }}</p>
                      
              </div>
          </div>
          <div class="w-56 h-48 bg-slate-300" >
              <div class="bg-orange-600 h-9">
                <h2 class=" pt-1 text-center text-white font-semibold">MODULO 2</h2>
              </div>
              <div class="">
                <p class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">1-WW99</p>
                <p class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">1-JKPL</p>
                         
              </div>
          </div>
          <div class="w-56 h-48 bg-slate-300 mr-10" >
              <div class="bg-green-700 h-9">
                <h2 class=" pt-1 text-center text-white font-semibold">MODULO 3</h2>
              </div>
              <div class="">
                <p class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">1-LOJ7</p>
                <p class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">1-NMKI</p>
                <p class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">1-GHJK</p>
                         
              </div>
          </div>
        </div>

        <div class="flex justify-between mt-8 bg-slate-300 h-16 items-center mx-auto w-[43rem] rounded-lg">
            <div class="">
                <h2 class="ml-10">TURNOS</h2>
            </div>

            <div class="flex space-x-3 mr-6">
                <input class="h-8 w-32 rounded-lg" type="text" placeholder="Codigo">
                <select class="h-8 w-32 rounded-lg" name="" id="">
                    
                 <option>Modulo 1</option>
                 <option>Modulo 2</option>
                 <option>Modulo 3</option>
                </select>
                <p class="bg-purple-700 h-8 px-4 rounded-lg text-white">Agregar Turno</p>
            </div>
        </div>


    </div>

</template> -->






<!-- <script setup>
import { ref, computed } from 'vue';

// Reactive data for each module
const datosModulo1 = ref([
  "XDCHH",
  "HT550",
  "G3WQ",
  "PTWE"
]);

const datosModulo2 = ref([
  "WW99",
  "JKPL"
]);

const datosModulo3 = ref([
  "LOJ7",
  "NMKI",
  "GHJK"
]);

const newCodigo = ref("");
const selectedModulo = ref("Modulo 1");

function addTurno() {
  if (newCodigo.value.trim() !== "") {
    if (selectedModulo.value === "Modulo 1") {
      datosModulo1.value.push(newCodigo.value);
    } else if (selectedModulo.value === "Modulo 2") {
      datosModulo2.value.push(newCodigo.value);
    } else if (selectedModulo.value === "Modulo 3") {
      datosModulo3.value.push(newCodigo.value);
    }
    newCodigo.value = "";
  }
}

const totalTurnos = computed(() => {
  return datosModulo1.value.length + datosModulo2.value.length + datosModulo3.value.length;
});
</script>

<template>
  <div class="w-[49rem] h-[30rem] bg-slate-100 mx-auto mt-20 shadow-2xl shadow-gray-600 border border-gray-500">
    <div class="pt-12">
      <h1 class="text-center font-bold">SISTEMA DE TURNOS</h1>
    </div>
    <div class="flex justify-evenly mt-3">
      <div class="w-56 h-48 bg-slate-300 ml-10">
        <div class="bg-cyan-500 h-9">
          <h2 class="pt-1 text-center text-white font-semibold">MODULO 1</h2>
        </div>
        <div>
          <p v-for="(dato, i) in datosModulo1" :key="i" class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">{{ i + 1 }}-{{ dato }}</p>
        </div>
      </div>
      <div class="w-56 h-48 bg-slate-300">
        <div class="bg-orange-600 h-9">
          <h2 class="pt-1 text-center text-white font-semibold">MODULO 2</h2>
        </div>
        <div>
          <p v-for="(dato, i) in datosModulo2" :key="i" class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">{{ i + 1 }}-{{ dato }}</p>
        </div>
      </div>
      <div class="w-56 h-48 bg-slate-300 mr-10">
        <div class="bg-green-700 h-9">
          <h2 class="pt-1 text-center text-white font-semibold">MODULO 3</h2>
        </div>
        <div>
          <p v-for="(dato, i) in datosModulo3" :key="i" class="bg-slate-100 mt-2 ml-3 mr-3 rounded-sm">{{ i + 1 }}-{{ dato }}</p>
        </div>
      </div>
    </div>

    <div class="flex justify-between mt-8 bg-slate-300 h-16 items-center mx-auto w-[43rem] rounded-lg">
      <div>
        <h2 class="ml-10">TURNOS: {{ totalTurnos }}</h2>
      </div>

      <div class="flex space-x-3 mr-6">
        <input v-model="newCodigo" class="h-8 w-32 rounded-lg" type="text" placeholder="Codigo">
        <select v-model="selectedModulo" class="h-8 w-32 rounded-lg">
          <option>Modulo 1</option>
          <option>Modulo 2</option>
          <option>Modulo 3</option>
        </select>
        <button @click="addTurno" class="bg-purple-700 h-8 px-4 rounded-lg text-white">Agregar Turno</button>
      </div>
    </div>
  </div>
</template> -->