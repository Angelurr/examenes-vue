<script setup>
import { ref } from 'vue';

const archivos = ref([
    {
       nombre:"Home", icon:"🏠" 
    },
    {
        nombre:"Gallery",icon: "📑"
    },
    {
        nombre:"OneDrive-Personal", icon: "☁️",
        hijo: [{
        nombre: "Documentos", icon: "📁",
        hijo: [{
            nombre: "Anvsoft", icon: "📁",
            hijo:[{
                nombre: "Juegos", icon: "📁"
            }]
        },
        {
            nombre: "Captura", icon: "📁" 
        },
        {
            nombre: "ClickCharts", icon: "📁"
        },
        {
            nombre: "Custom Office Template", icon: "📁"
        },
        {
            nombre: "OneNota Notebook", icon: "📁"
        },
        {
            nombre: "Sound Recordings", icon: "📁"
        },
        {
            nombre: "Zoom", icon: "📁"
        }]

        

            
       }]
    },
    {
        nombre:"Pictures", icon: "📁"
    },
    {
        nombre:"TWS", icon: "📁"
    },


])

let indiceSeleccionado = ref(-1);
function desplegar(i){
   if(indiceSeleccionado.value == i){
     indiceSeleccionado.value = -1;
   }else{
    indiceSeleccionado.value = i;
   }
}

let indiceSeleccionado2 = ref(-1);
function desplegar2(j){
    if(indiceSeleccionado2.value == j){
     indiceSeleccionado2.value = -1;
   }else{
    indiceSeleccionado2.value = j;
   }
    
}
let indiceSeleccionado3 = ref(-1);
function desplegar3(k){
    if(indiceSeleccionado3.value == k){
     indiceSeleccionado3.value = -1;
   }else{
    indiceSeleccionado3.value = k;
   }
    
}
let indiceSeleccionado4 = ref(-1);
function desplegar4(f){
    if(indiceSeleccionado4.value == f){
     indiceSeleccionado4.value = -1;
   }else{
    indiceSeleccionado4.value = f;
   }
    
}



</script>

<template>
    <div class="bg-slate-100 w-[18rem] h-[30rem] mx-auto mt-8 border border-black">
       <div class="pt-4">
         <div  class="px-2  select-none"  v-for="(archivo,i) in archivos":key="i">
            <span>{{ indiceSeleccionado == i ?"v":">" }}</span> <span @click="desplegar(i)" class="cursor-pointer hover:bg-slate-400"  >{{ archivo.icon }}{{ archivo.nombre }}</span>
            <div  v-show="indiceSeleccionado == i">
                <div class="px-2 "  v-for="(hijo1,j) in archivo.hijo":key="j" >
                 <span>{{ indiceSeleccionado2 == j ?"v":">" }}</span><span @click="desplegar2(j)" class="cursor-pointer hover:bg-slate-400" >{{ hijo1.icon }}{{ hijo1.nombre }}</span>
                 <div v-show="indiceSeleccionado2 == j">
                    <div class="px-2"  v-for="(hijo2,k) in hijo1.hijo":key="k">
                    <span>{{ indiceSeleccionado3 == k ?"v":">" }}</span><span @click="desplegar3(k)" class="cursor-pointer hover:bg-slate-400" >{{ hijo2.icon }}{{ hijo2.nombre }}</span>
                    <div  v-show="indiceSeleccionado3 == k" >
                     <div class="px-2"  v-for="(hijo3,f) in hijo2.hijo":key="f"><span>{{ indiceSeleccionado4 == f ?"v":">" }}</span><span @click="desplegar4(f)" class="cursor-pointer hover:bg-slate-400" >{{ hijo3.icon }}{{ hijo3.nombre }}</span></div>
                    </div>
                    
                    </div>
                </div>
                
             </div>
            </div>
        
         </div>

       </div>
        
    </div>
    


</template>