<script setup>
import { ref } from 'vue';


let mas;
let sumador = ref(0);
let numero = 120000;
let total = ref(0)
let total1 = ref(0)
let envio = 15000;

let comprador = ref({
  nombres: '',
  correo: '',
  direccion: '',
  metodoPago: ''
});


let nombres = ref('');
let correo = ref('');
let direccion = ref('');
let metodoPago = ref('');



function insertar() {
  comprador.value.nombres = nombres.value;
  comprador.value.correo = correo.value;
  comprador.value.direccion = direccion.value;
  comprador.value.metodoPago = metodoPago.value;
  
  
}





function suma() {
    sumador.value++;
    
}
function sub(){
    total.value=sumador.value*numero;
}
function subresta(){
    if(sumador.value >= 0){
        total.value=sumador.value*numero;
    }
}

function resta() {
    if(sumador.value > 0){
        sumador.value--;
    }

}
function totalfinal(){
   total1.value=numero*sumador.value+envio;

}
function totalfinalresta(){
   
    if(sumador.value >= 0){
        total1.value=numero*sumador.value;
    }
   

}








</script>

<template>
    
    <div class="bg-blue-200 w-72 h-96 mx-auto mt-5">
        <div class="pt-7 ">
            <h2 class="font-bold  text-center">CARRITO DE COMPRAS</h2>
            <img class="w-56 h-36 mt-1 mx-auto rounded-lg" src="https://www.tennisnuts.com/images/product/full/CZ0220-324_E.jpg" alt="">
               
        </div>
        
        <div class="flex justify-evenly items center">
                <h2 class="mr-12">Tenis casuales</h2>
                
                <div class="flex justify-center ">
                    <div @click="resta(), subresta(), totalfinalresta()" class="bg-slate-200 w-4 h-4 mt-1 ">
                        <p class= " text-center">-</p>
                    </div>
                    <h2 class="mr-1 ml-1" >{{ sumador }}</h2>
                    <div @click="suma(), sub(), totalfinal()"  class="bg-slate-200 w-4 h-4 mt-1 ">
                        <p class= "pb-4 text-center" >+</p>
                    </div>
                </div>
               
        </div>
        <div class="ml-8">
            <p class="font-bold" >120.000</p>
        </div>
        <div  class="flex justify-between mt-2">
            <p class="ml-8" >Sub total</p>
            <p class="mr-10">{{ total }}</p>
        </div>
        <div class="flex justify-between ">
            <p class="ml-8" >Envio</p>
            <p class="mr-10">15.000</p>
        </div>
        <div class="flex justify-between ">
            <p class="ml-8 font-bold" >Total</p>
            <p class="mr-10 font-bold">{{ total1 }}</p>
        </div>
        <div class="flex justify-end bg-green-600 mt-2 mr-5 ml-44 h-7 rounded-lg">
            <p class=" mr-3  text-white " >Continuar</p>

        </div>

    </div>

    <div class="bg-blue-200 w-72 h-96 mx-auto mt-5">
        <div class="pt-7">
            <h1 class="font-bold ml-6">Datos del comprador</h1>
        </div>
       <div class="">
           <div class="ml-6">
            <label for="">Nombres y Apellidos</label>
           </div>
        
         <div class="flex justify-center">
            <input class="w-60 rounded-lg h-8" type="text" v-model="nombres">
         </div>
       </div>
       <div class="mt-3">
           <div class="ml-6">
            <label for="">Correo electronico</label>
           </div>
        
         <div class="flex justify-center">
            <input class="w-60 rounded-lg h-8" type="text" v-model="correo">
         </div>
       </div>
       <div class="mt-3">
           <div class="ml-6">
            <label for="">Direccion</label>
           </div>
        
         <div class="flex justify-center">
            <input class="w-60 rounded-lg h-8" type="text" v-model="direccion">
         </div>
       </div>
       <div class="mt-3">
           <div class="ml-6">
            <label for="">Metodo de pago</label>
           </div>
        
         <div class="flex justify-center">
            <input class="w-60 rounded-lg h-8" type="text" v-model="metodoPago">
         </div>
       </div>
       <div class="flex justify-end bg-green-600 mt-6 mr-5 ml-44 h-7 rounded-lg">
            <p @click="insertar(),totalfinal()" class=" mr-3  text-white " >Continuar</p>

        </div>

    </div>

    <div class="bg-blue-200 w-72 h-96 mx-auto mt-5">
        <div class="pt-7">
            <h1 class="font-bold ml-6">Resumen de la compra</h1>
        </div>
        <div class="mt-4">
            <h1 class="ml-6" >Producto</h1>
            <h2 class="ml-6 font-bold" >Tenis casuales</h2>
        </div>

    
        <div class="mt-3">
            <h2 class="ml-6 text-gray-500" >Cliente</h2>
            <p class="ml-6" > {{ comprador.nombres }}</p>
            <p class="ml-6" > {{ comprador.correo }}</p>
            <p class="ml-6" > {{ comprador.direccion }}</p>
            <p class="ml-6" > {{ comprador.metodoPago }}</p>
        </div>
        <div class="mt-4 flex justify-end ">
            
            <p class="mr-6 "><h2>Valor a pagar</h2> <h3 class="text-green-600 font-bold text-3xl" >{{ total1 }}</h3></p>

        </div>
        <div class="flex justify-end bg-green-600 mt-6 mr-5 ml-48 h-7 rounded-lg">
            <p class=" mr-3  text-white " >Pagar</p>

        </div>

    </div>


</template>