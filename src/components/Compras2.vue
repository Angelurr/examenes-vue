<script setup>
import {ref} from 'vue'

let page1 = ref(true)
let page2 = ref(false)
let page3 = ref(false)
let precio = 290000
let envio = 30000
let cantidad = ref(0)
let subtotal = ref(0)
let total = ref(0)
let nombre = ref('')
let producto = 'Botines Futbol Nike'

function cantidad1(){
    if(cantidad.value > 0)
    cantidad.value--
}
function cantidad2(){
    cantidad.value++
    if(cantidad.value == 1){
        subtotal.value = precio
    }
    if(cantidad.value >= 2){
        subtotal.value = precio + subtotal.value
    } 
    total.value = subtotal.value + envio
}

function show1(){
    page1.value = false
    page2.value = true
}
function show2(){
    page2.value = false
    page3.value = true
}



</script>

<template>

<div v-if="page1" class="bg-blue-600 w-[50%] mt-5 mx-auto py-20 px-10 rounded-md container">
    <div class="mb-10 rounded-md mx-auto">
        <img src="https://unitedstorecolombia.com/cdn/shop/products/72770d25.jpg?v=1680383037&width=1445" alt="" class="rounded-lg h-80 w-[450px] mx-auto">
    </div>
    <div>
        <div class="ml-16 text-2xl text-white font-semibold" >
        Botines Futbol Nike
            <div class="inline-block float-right mr-16" >
                <div class="" ><button @click="cantidad1" class="mr-3 rounded-md bg-slate-400 px-2">-</button><span>{{ cantidad }}</span><button @click="cantidad2" class="ml-3 rounded-md bg-slate-400 px-2" >+</button></div>
            </div>
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
        Precio: 290000
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
        Subtotal: <span>{{ subtotal }}</span>
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
        Envío: 30000
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
        Total: <span>{{ total }}</span>
        </div>
        <div @click="show1" class="hover:cursor-pointer float-right bg-slate-200 rounded-md py-2 px-4 mb-10 mt-5" >Continuar</div>
    </div>
</div>
<div v-if="page2" class="bg-blue-600 w-[60%] mt-10 mx-auto py-24 px-10 rounded-md container">
    <div class="text-center mb-5"><H1 class="font-semibold text-4xl">Datos de Envio</H1></div>
    <div class="bg-slate-600 rounded-md py-10" >
        <div class="ml-16 text-2xl text-white font-semibold" >
            Nombre: 
            <input v-model="nombre" type="text" class="rounded-md ml-4 float-right mr-5 text-black focus:outline-none px-1"  >
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
            Email: 
            <input type="text" class="rounded-md ml-4 float-right mr-5 text-black focus:outline-none px-1" >
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
            Direccion: 
            <input type="text" class="rounded-md ml-4 float-right mr-5 text-black focus:outline-none px-1" >
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
            Metodo de Pago:
            <input type="text" class="rounded-md ml-4 float-right mr-5 text-black focus:outline-none px-1" >
        </div>
        <div @click="show2" class="hover:cursor-pointer float-right bg-slate-200 rounded-md py-2 px-4 mb-20 mt-12" >Continuar</div>

    </div>
</div>
<div v-if="page3" class="bg-blue-600 w-[50%] mt-10 mx-auto py-24 px-10 rounded-md container">
    <div class="text-center mb-5"><H1 class="font-semibold text-4xl">Detalles De Compra</H1></div>
    <div class="bg-slate-600 rounded-md py-10" >
        <div class="ml-16 text-2xl text-white font-semibold" >
            A Nombre de: <span>{{ nombre }}</span>
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
            Producto: <span>{{ producto }}</span>    
        </div>
        <div class="ml-16 text-2xl text-white font-semibold mt-4" >
            Valor Total: <span>{{ total }}</span> 
        </div>
        <div @click="" class="hover:cursor-pointer float-right bg-slate-200 rounded-md py-2 px-4 mb-20 mt-12" >Pagar</div>
    </div>
</div>

</template>