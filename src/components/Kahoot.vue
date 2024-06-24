<script setup>
import { ref } from 'vue';

const aplicacions = ref([
    {
        pregunta: "¿De qué país es James Rodríguez?",
        color: "UFPSO",
       
        
        hijo: [
            { respuestas: "Colombia", valor: true },
            { respuestas: "Brasil", valor: false },
            { respuestas: "Perú", valor: false },
            { respuestas: "Canadá", valor: false }
        ]
    },
    {
        pregunta: "¿Quien es el mejor programador?",
        color: "UFPSO",
       
        
        hijo: [
            { respuestas: "Mateo", valor: false },
            { respuestas: "Fraider", valor: false },
            { respuestas: "Yohan", valor: true },
            { respuestas: "Angel", valor: false }
        ]
    }
]);

const colores = [
    "bg-red-500",
    "bg-green-500",
    "bg-blue-500",
    "bg-yellow-500"


]
    
    





let colorCorrecto = ref("bg-blue-500");
function respuestaColor(respuesta){
   
    if(respuesta.valor){
        colorCorrecto.value = 'bg-green-500';
        correcta.value = respuesta.valor;
        

    }else{
        colorCorrecto.value = 'bg-red-500';
        correcta.value = respuesta.valor;
    }
   

}
let click = ref(true)
let correcta = ref(null);
let indice = ref(0);
let enseñarPregunta = ref(aplicacions.value[indice.value].pregunta);
let enseñarRespuesta = ref(aplicacions.value[indice.value].hijo)
function respuestaCorrecta(){
    if(correcta.value !== null){
      
    if(indice.value < aplicacions.value.length){
        indice.value++;
        actualizarPregunta();
        
       
        
    }


    }else{
        alert("seleccione una respuesta")

    }

}
let contadorCorrectas = ref(0)
let contadorIncorrectas = ref(0)
function contador(j){
    const respuestacons =enseñarRespuesta.value[j]
    if(click.value){
        click.value = false;
        if(respuestacons.valor){
        contadorCorrectas.value++;
        

    }else{
        contadorIncorrectas.value++;
    }
    respuestaColor(respuestacons);
    }


}


function actualizarPregunta(){
    if(indice.value < aplicacions.value.length){
        enseñarPregunta.value = aplicacions.value[indice.value].pregunta;
        enseñarRespuesta.value = aplicacions.value[indice.value].hijo;
        colorCorrecto.value = "bg-blue-500";
        click.value= true;
        correcta.value=null;


    }
}











</script>

<template>
     <div class="bg-slate-400 w-[40rem] h-[28rem] mx-auto mt-4">
        <div>
            <div v-if="indice < aplicacions.length">
                <div class="text-center">
                    <div>{{ enseñarPregunta }}</div>
                    <div :class="colorCorrecto" class="bg-blue-600 w-[20rem] h-[12rem] mt-4 mx-auto"><h1 class="text-5xl pt-6 text-white" >UFPSO</h1></div>
                    <div class="mt-2 grid grid-cols-2 gap-2">
                        <div  v-for="(respuesta, j) in enseñarRespuesta" :key="j">
                            <div @click="contador(j)" class="px-20 py-2" :class="[colores[j]]">{{ respuesta.respuestas }}</div>
                        </div>
                    </div>
                    <div class="flex justify-end">
                        <div class="bg-blue-600 w-20 mt-3 rounded-sm">
                            <button @click="respuestaCorrecta" class="text-white">Siguiente</button>
                        </div>
                    </div>
                </div>
            </div>
            <div v-else>
                <div class="text-center">
                    <div class="text-xl">Quiz finalizado</div>
                    <div>Correctas: {{ contadorCorrectas }}</div>
                    <div>Incorrectas: {{ contadorIncorrectas }}</div>
                </div>
            </div>
        </div>
    </div>
</template>



