
<script setup>
import { ref } from 'vue';

let contador = ref(29);

let contador1 = ref(3);
function likes(){
    contador.value++;

}
function Dislikes(){
    contador1.value++;

}


// let likes = ref(27)
// let dislikes = ref(0)
// let start = ref(false)
// let start1 = ref(false)

// function counter(){
//     if(dislikes.value == 0){
//         likes.value =28
//     }
// }
// function counter2(){
//     if(likes.value == 0){
//         likes.value =28
//         start1.value = true;
//     }
// }





// import { ref } from 'vue';

// let contador = ref(29);
// let contador1 = ref(3);

// let hasLiked = ref(false);
// let hasDisliked = ref(false);

// function likes() {
//     if (!hasLiked.value && !hasDisliked.value) {
//         contador.value++;
//         hasLiked.value = true;
//     }
// }

// function Dislikes() {
//     if (!hasLiked.value && !hasDisliked.value) {
//         contador1.value++;
//         hasDisliked.value = true;
//     }
// }






</script>


<template>
    <div class=" bg-slate-100  h-[50rem] w-[34rem] mx-auto mt-8 mb-6 shadow-2xl border border-gray-600">
        <div class="mt-6 flex justify-between ml-8 mr-8">
            <div class="">
                <h2 class="font-bold">Historias</h2>
            </div>
            <div class="bg-sky-500 rounded-lg w-14 h-7 pl-2">
                <h2 class="text-white">Todas</h2>
            </div>
        </div>

        <div class="flex justify-around mt-4 mr-6 ml-6">
            <div>
                <div class="border-[5px] border-blue-600 rounded-xl bg-[url('https://1.bp.blogspot.com/-ALOKr9KPAos/W-tMA9xWChI/AAAAAAAABw0/2V6EnscdpAMTKvAhkGEqO8YRAtjAkvtPACLcBGAs/s640/cfcgvhvh.jpg')] w-28 h-28 bg-[length:130%_100%]">
               
                </div>
                <div><h2>adasdas</h2></div>
            </div>
            <div>
                <div class="border-[5px] border-blue-600 rounded-xl bg-[url('https://1.bp.blogspot.com/-ALOKr9KPAos/W-tMA9xWChI/AAAAAAAABw0/2V6EnscdpAMTKvAhkGEqO8YRAtjAkvtPACLcBGAs/s640/cfcgvhvh.jpg')] w-28 h-28 bg-[length:130%_100%]">
               
                </div>
                <div><h2>adasdas</h2></div>
            </div>
            <div>
                <div class="border-[5px] border-blue-600 rounded-xl bg-[url('https://1.bp.blogspot.com/-ALOKr9KPAos/W-tMA9xWChI/AAAAAAAABw0/2V6EnscdpAMTKvAhkGEqO8YRAtjAkvtPACLcBGAs/s640/cfcgvhvh.jpg')] w-28 h-28 bg-[length:130%_100%]">
               
                </div>
                <div><h2>adasdas</h2></div>
            </div>
            <div>
                <div class="border-[5px] border-blue-600 rounded-xl bg-[url('https://1.bp.blogspot.com/-ALOKr9KPAos/W-tMA9xWChI/AAAAAAAABw0/2V6EnscdpAMTKvAhkGEqO8YRAtjAkvtPACLcBGAs/s640/cfcgvhvh.jpg')] w-28 h-28 bg-[length:130%_100%]">
               
                </div>
                <div><h2>adasdas</h2></div>
            </div>
            
            
        </div>
        <div class="flex justify-between mt-6 mr-8 ml-8">
            <div class="flex justify-center">
                <img class="w-12 h-12 rounded-full" src="https://br.web.img3.acsta.net/pictures/19/05/22/10/42/3773139.jpg" alt="">
               <div class="ml-1">
                <h2 class="font-bold " >Mariano Perez</h2>
                <p class="">Hace 10 minutos</p>
               </div>
            </div>
            <div>
                <h2 class="font-bold text-red-700 mt-6">Reportar</h2>
            </div>
        </div>

        <div class="mt-4">
            <div class="rounded-2xl ml-8 bg-[url('https://www.anipedia.net/imagenes/que-comen-los-perros.jpg')] w-[30rem] h-[25rem] bg-[length:130%_100%]"></div>
            <div class="ml-8 flex justify-start mt-2">
                <svg @click="likes()" class="w-6 h-6 " xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="m12.1 18.55l-.1.1l-.11-.1C7.14 14.24 4 11.39 4 8.5C4 6.5 5.5 5 7.5 5c1.54 0 3.04 1 3.57 2.36h1.86C13.46 6 14.96 5 16.5 5c2 0 3.5 1.5 3.5 3.5c0 2.89-3.14 5.74-7.9 10.05M16.5 3c-1.74 0-3.41.81-4.5 2.08C10.91 3.81 9.24 3 7.5 3C4.42 3 2 5.41 2 8.5c0 3.77 3.4 6.86 8.55 11.53L12 21.35l1.45-1.32C18.6 15.36 22 12.27 22 8.5C22 5.41 19.58 3 16.5 3"/></svg>
                
                <p>{{ contador }}</p>
                <svg @click="Dislikes()" class="ml-6 w-6 h-6" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M7.498 15.25H4.372c-1.026 0-1.945-.694-2.054-1.715a12 12 0 0 1-.068-1.285c0-2.848.992-5.464 2.649-7.521C5.287 4.247 5.886 4 6.504 4h4.016a4.5 4.5 0 0 1 1.423.23l3.114 1.04a4.5 4.5 0 0 0 1.423.23h1.294M7.499 15.25c.618 0 .991.724.725 1.282A7.5 7.5 0 0 0 7.5 19.75A2.25 2.25 0 0 0 9.75 22a.75.75 0 0 0 .75-.75v-.633c0-.573.11-1.14.322-1.672c.304-.76.93-1.33 1.653-1.715a9 9 0 0 0 2.86-2.4c.498-.634 1.226-1.08 2.032-1.08h.384m-10.253 1.5H9.7m8.075-9.75q.015.075.05.148a8.95 8.95 0 0 1 .925 3.977a8.95 8.95 0 0 1-.999 4.125m.023-8.25c-.076-.365.183-.75.575-.75h.908c.889 0 1.713.518 1.972 1.368c.339 1.11.521 2.287.521 3.507c0 1.553-.295 3.036-.831 4.398c-.306.774-1.086 1.227-1.918 1.227h-1.053c-.472 0-.745-.556-.5-.96a9 9 0 0 0 .303-.54"/></svg>
                <p>{{ contador1 }}</p>
            </div>
        </div>

        <div class="bg-slate-300 mt-4 ml-8 mr-8 rounded-xl h-14">
            <div class="flex justify-around ">
                <svg class="w-10 h-10 mt-2" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15.75 6a3.75 3.75 0 1 1-7.5 0a3.75 3.75 0 0 1 7.5 0M4.501 20.118a7.5 7.5 0 0 1 14.998 0A17.9 17.9 0 0 1 12 21.75c-2.676 0-5.216-.584-7.499-1.632"/></svg>
                <div class="bg-slate-100 mt-2 rounded-xl w-12 h-11">
                    <svg class="w-10 h-10 ml-1 " xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 256 256"><path fill="currentColor" d="M240 208h-16v-72l2.34 2.34A8 8 0 0 0 237.66 127l-98.35-98.32a16 16 0 0 0-22.62 0L18.34 127a8 8 0 0 0 11.32 11.31L32 136v72H16a8 8 0 0 0 0 16h224a8 8 0 0 0 0-16M48 120l80-80l80 80v88h-48v-56a8 8 0 0 0-8-8h-48a8 8 0 0 0-8 8v56H48Zm96 88h-32v-48h32Z"/></svg>
                </div>
                <svg class="w-10 h-10 mt-2" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 512 512"><path fill="none" stroke="currentColor" stroke-miterlimit="10" stroke-width="32" d="M221.09 64a157.09 157.09 0 1 0 157.09 157.09A157.1 157.1 0 0 0 221.09 64Z"/><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-miterlimit="10" stroke-width="32" d="M338.29 338.29L448 448"/></svg>

                
            </div>
        </div>

    </div>
</template>



















<!-- <template>
    
    
    <div class="w-full h-screen justify-center flex">

<div class="w-2/5 p-4 border border-1 mx-auto m-4 shadow-sm shadow-black">
<div class="">
   <div class="w-full flex justify-between text-[20px]">
       <h1 class="font-bold">Historias</h1>
       <h2 class="bg-[#1DACD6] px-8 text-white rounded-lg">Todas</h2>
   </div>
   <div class="flex justify-evenly mt-3">
       <div>
           <div class="hover:border-[#0cb7fd] bg-[length:130%_100%] bg-no-repeat bg-center w-28 h-28 border-[5px] border-blue-600 rounded-xl bg-[url('https://wallpaperaccess.com/full/1398619.jpg')]">
           </div>
           <div class=""><h2>Camila</h2></div>
       </div>
       <div>
           <div class="hover:border-[#0cb7fd] bg-[length:130%_100%] bg-no-repeat bg-center w-28 h-28 border-[5px] border-blue-600 rounded-xl bg-[url('https://wallpaperaccess.com/full/1398619.jpg')]">
           </div>
           <div class=""><h2>Camila</h2></div>
       </div>
       <div>
           <div class="hover:border-[#0cb7fd] bg-[length:130%_100%] bg-no-repeat bg-center w-28 h-28 border-[5px] border-blue-600 rounded-xl bg-[url('https://wallpaperaccess.com/full/1398619.jpg')]">
           </div>
           <div class=""><h2>Camila</h2></div>
       </div>
       <div>
           <div class="hover:border-[#0cb7fd] bg-[length:130%_100%] bg-no-repeat bg-center w-28 h-28 border-[5px] border-blue-600 rounded-xl bg-[url('https://wallpaperaccess.com/full/1398619.jpg')]">
           </div>
           <div class=""><h2>Camila</h2></div>
       </div>
       

   </div>
   
   
</div>
<div class="mt-6">
   <div class="flex justify-between">
       <div class="flex ">
           <img class=" rounded-full w-12 h-12" src="https://tse1.mm.bing.net/th?id=OIP.FZn8OcD83im6ZoqT13ePkAHaHa&pid=Api&P=0&h=180" alt="">
           <h2 class="ml-4 mb-8 font-bold">Mariano Perez</h2>
           
       </div>
       <h2 class="text-red-700 font-bold">Reportar</h2>
   </div>
</div>
<div class="flex justify-center ">
   <div>
       <img class="w-96 h-60 rounded-2xl" src="https://www.anipedia.net/imagenes/que-comen-los-perros.jpg" alt="">
   </div>
   
</div>
<div>
    <Icon name="mdi:cards-heart-outline" />
    <p>adasd</p>
   
</div>




<div class="bg-slate-400 rounded-2xl h-10 ">
   <div class="flex justify-evenly">
       
   </div>

</div>



 </div>


</div>

</template> -->