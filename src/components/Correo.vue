<script setup>
function cambiarEstilo(index) {
    correos.value[index].leido = !correos.value[index].leido;
}

</script>
<template>
    <div class="flex text-black justify-center text-6xl mb-10">
        Correo
    </div>
    
    <div class="bg-slate-500 w-[50%] ml-28">
        <section class="max-w-6xl mx-auto grid grid-cols-2 w-[50%]">
            <div class=" grid grid-cols-1 gap-4 ">
                <div 
                    v-for="(correo, index) in correos" 
                    :key="index" 
                    @click="cambiarEstilo(index)" 
                    :class="{
                        'border-4 border-black': !correo.leido,
                        'bg-slate-300': correo.leido,
                        'cursor-pointer': true,
                        'h-32 w-96': true
                    }"
                >
                    {{ correo.asunto }}
                    <br>
                    {{ correo.texto }}
                </div>
            </div>
        </section>
    </div>
</template>