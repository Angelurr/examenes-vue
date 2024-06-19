<!-- <script setup>
import { ref } from 'vue';

let index =ref(0);

 let mensajes = [{
    name: "Marcos Perez",
    mensaje1: "Hola, espero que estes muy bien",
    mensaje2: "Necesito un favor tuyo",
    mensaje3: "Cuando te conectes por favor me contestas y te cuento lo que necesito. Gracias"
 },
 {
    name: "Juana Contreras",
    mensaje1: "holaaa",
    mensaje2: "holaaa",
    mensaje3: "holaaa"

 },
 {
    name: "Anonymous",
    mensaje1: "holaaa",
    mensaje2: "holaaa",
    mensaje3: "holaaa"

 }]

 function clickArray(indice){
    index.value= indice;


 }

 

</script>
<template>
   
    <div class="bg-slate-900 w-3/4 h-screen mx-auto ">
        <div class="flex justify-center text-white h-full">
            <div class="h-full ">
                <div class="ml-3 mt-4 w-10 h-screen ">
                <img class="w-8 h-8 rounded-xl" src="https://i.pinimg.com/originals/9b/d1/45/9bd1452b9b0f977d8bae8d31d736adbd.jpg" alt="">
                <h2>Perfil</h2>
                </div>
            </div>
           

            <div class="h-full flex-grow w-20 bg-slate-800">
               <div class="mt-6 ml-3">
                <h2>TENDENCIAS</h2>
                <p class="mt-2">#titanic</p>
                <p>#titanic</p>
                <p>#titanic</p>
                <p>#titanic</p>
                <p>#titanic</p>
                <p >#titanic</p>

               <h2 class="mt-24" >MENSAJES DIRECTOS</h2>
               
              
               
               <div @click="clickArray(0)" class="bg-slate-700 rounded-lg mr-2 mt-2 ">
                 <div class="flex ">
                    <div>
                        <img class="rounded-full w-10 h-10 ml-2 mt-1" src="https://i.pinimg.com/originals/9b/d1/45/9bd1452b9b0f977d8bae8d31d736adbd.jpg" alt="">
                    </div>
                    
                    <div>
                        <h2 class="ml-2" >Marcos perez</h2>
                        <h2 class="ml-2 " >Hace 10 minutos</h2>
                    </div>
                      
                 </div>
                </div>
               <div @click="clickArray(1)" class="bg-slate-700 rounded-lg mt-2 mr-2">
                 <div class="flex ">
                    <div>
                        <img class="rounded-full w-10 h-10 ml-2 mt-1" src="https://i.pinimg.com/originals/9b/d1/45/9bd1452b9b0f977d8bae8d31d736adbd.jpg" alt="">
                    </div>
                    
                    <div>
                        <h2 class="ml-2" >Juana Contreras</h2>
                        <h2 class="ml-2 " >Ayer</h2>
                    </div>
                      
                 </div>
                </div>
                
    
               <div @click="clickArray(2)" class="bg-slate-700 rounded-lg mt-2 mr-2">
                 <div class="flex ">
                    <div>
                        <img class="rounded-full w-10 h-10 ml-2 mt-1" src="https://i.pinimg.com/originals/9b/d1/45/9bd1452b9b0f977d8bae8d31d736adbd.jpg" alt="">
                    </div>
                    
                    <div>
                        <h2 class="ml-2" >Anonymous</h2>
                        <h2 class="ml-2 " >Hace 10 minutos</h2>
                    </div>
                      
                 </div>
                </div>
               </div>
            </div>

            <div class="h-full flex-grow mt-3 ml-3 ">
                <div>
                   
  <div class="p-2">
    <div class="text-gray-300 text-xl">{{ mensajes[index].name }}</div>
    <div class="bg-gray-900 rounded-lg w-72 h-20 p-4 mt-6 border border-slate-500">
      <div><h1 class="text-gray-300 ">{{ mensajes[index].mensaje1 }}</h1></div>
      <div><p class="text-slate-700 flex justify-end">25/06/2009 10:50 AM</p></div>
    </div>

    <div class="bg-gray-900 border border-slate-500 mt-6 rounded-lg w-72 h-20">
      <div> <h1 class="text-gray-300 mt-3 ml-3"> {{mensajes[index].mensaje2 }}</h1></div>
      <div class="flex justify-end mt-2 mr-3 text-slate-700"> 25/06/2009 10:50 AM </div>
    </div>

    <div class="bg-gray-900 border border-slate-500 mt-6 rounded-lg w-72 h-24">
    <div> <h1 class="text-gray-300 mt-3 ml-3"> {{ mensajes[index].mensaje3 }} </h1></div>
    <div class=" flex justify-end mt-2 mr-3 text-slate-700 "> 25/06/2009 10:50 AM </div>
    </div>
  </div>
    </div>
    </div>


            <div class="h-screen w-10 bg-slate-800 flex-grow  ml-3  ">
                <div>
                <h2 class="mt-6 ml-6" >PUBLICIDAD</h2>
                <img class="w-48 h-48 mt-3 mx-auto rounded-xl" src="https://crehana-blog.imgix.net/media/filer_public/90/83/9083027a-fc03-4e3f-8f55-636ffce6d36c/mcdonalds-happy-meal.jpg?auto=format&q=50" alt="">
                <img class="w-48 h-48 mt-2 mx-auto rounded-xl" src="https://crehana-blog.imgix.net/media/filer_public/90/83/9083027a-fc03-4e3f-8f55-636ffce6d36c/mcdonalds-happy-meal.jpg?auto=format&q=50" alt="">
                </div>
            </div>
        </div>
    </div>
    

</template> -->