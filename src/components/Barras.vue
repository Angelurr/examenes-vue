<!-- <script setup>
import { ref } from 'vue';

const texto = ref('');
const contador = ref(0);

function medidor() {
contador.value = texto.value.trim().split(/\s+/).length;
console.log(contador.value);
}


</script>
<template>
    <div class="w-full h-screen flex items-center">
        <video autoplay loop muted playsinline class="absolute inset-0 w-full h-full object-cover z-[-1]">
      <source src="https://cdn.pixabay.com/video/2019/10/11/27770-365891067_large.mp4" type="video/mp4">
      Tu navegador no soporta el video.
    </video>

        <div class="mx-auto w-2/4  text-center  flex-col">
            <div class=" mx-auto w-2/5 justify-center flex items-end space-x-3">

                <div class="bg-red-600 w-8 h-[40px]" v-if="contador >= 1 "></div>
                <div class="bg-slate-400 w-8 h-[40px]" v-else></div>
                <div class="bg-orange-600 w-8 h-[70px]" v-if="contador >= 3 "></div>
                <div class="bg-slate-400 w-8 h-[70px]" v-else></div>
                <div class="bg-yellow-600 w-8 h-[100px]" v-if="contador >= 5 "></div>
                <div class="bg-slate-400 w-8 h-[100px]" v-else></div>
                <div class="bg-green-600 w-8 h-[140px]" v-if="contador >= 7"></div>
                <div class="bg-slate-400 w-8 h-[140px]" v-else></div>

            </div>
            <div class="">
                <input v-model="texto" @input="medidor() class=" px-2 bg-white mt-10 h-11 rounded-lg border border-black " type="text">
                
            </div>
            

        </div>

    </div>

</template> -->