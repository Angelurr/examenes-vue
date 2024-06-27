<script setup>
import { ref } from 'vue';

// Datos reactivos para las preguntas y respuestas
const chats = ref([]);

// Datos individuales
const nombre = ref('');
const pregunta = ref('');
const respuesta = ref('');
const respuestaSecundaria = ref('');

// Función para insertar una nueva pregunta
function insertar() {
  if (nombre.value && pregunta.value) {
    chats.value.push({
      nombre: nombre.value,
      pregunta: pregunta.value,
      respuesta: '',
      respuestasSecundarias: [],
      likes: 0,
      dislikes: 0,
      haReaccionado: false
    });
    nombre.value = '';
    pregunta.value = '';
  }
}

// Función para insertar una respuesta a una pregunta específica
function insertar2(index) {
  if (respuesta.value) {
    chats.value[index].respuesta = respuesta.value;
    chats.value[index].mostrarResponder = false; // Oculta el campo de respuesta después de enviar
    respuesta.value = '';
  }
}

// Función para insertar una respuesta a una respuesta específica
function insertarSecundaria(index) {
  if (respuestaSecundaria.value) {
    chats.value[index].respuestasSecundarias.push({
      respuesta: respuestaSecundaria.value,
      likes: 0,
      dislikes: 0,
      haReaccionado: false
    });
    chats.value[index].mostrarResponderSecundaria = false; // Oculta el campo de respuesta secundaria después de enviar
    respuestaSecundaria.value = '';
  }
}

// Función para manejar las reacciones
function reaccionar(chat, tipo) {
  if (!chat.haReaccionado) {
    if (tipo === 'like') {
      chat.likes++;
    } else if (tipo === 'dislike') {
      chat.dislikes++;
    }
    chat.haReaccionado = true;
  }
}

function eliminar(index) {
  chats.value.splice(index, 1);
}
</script>

<template>
  <div class="bg-slate-400 w-[38rem] h-auto mx-auto pb-5 shadow-2xl border border-black border-[2px]">
    <div class="pt-4">
      <!-- Formulario para agregar una nueva pregunta -->
      <div class="bg-slate-200 w-[32rem] h-auto ml-10 rounded-lg p-4 mb-6">
        <div class="flex justify-start gap-2 ml-3 mt-2">
          <h2>Nombre:</h2>
          <input class="border border-black p-1" type="text" v-model="nombre">
        </div>
        <div class="flex justify-center gap-2 mt-2">
          <input class="border border-black w-[20rem] h-[5rem] p-2" type="text" placeholder="Pregunta" v-model="pregunta">
        </div>
        <div class="flex justify-end mr-20 mt-2">
          <button @click="insertar" class="bg-blue-500 rounded-sm text-white w-24 p-2">Preguntar</button>
        </div>
      </div>

      <!-- Desplegar preguntas y respuestas -->
      <div v-for="(chat, index) in chats" :key="index" class="bg-slate-200 w-[32rem] h-auto ml-10 rounded-lg mt-6 p-4">
        <div class="flex justify-around gap-4">
          <div class="flex items-center gap-6 mr-48">
            <img class="w-10 h-10 rounded-full" src="https://hips.hearstapps.com/hmg-prod/images/mh-celeb-name-changes-1567632828.png?crop=0.429xw:0.859xh;0.0321xw,0&resize=640:*" alt="">   
            <h2>{{ chat.nombre }}</h2>
          </div>
        </div>
        <div class="ml-20 mt-2">
          <h2>{{ chat.pregunta }}</h2>
        </div>
        <div class="flex justify-start ml-6 gap-4">
          <svg @click="reaccionar(chat, 'like')" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M23 10a2 2 0 0 0-2-2h-6.32l.96-4.57c.02-.1.03-.21.03-.32c0-.41-.17-.79-.44-1.06L14.17 1L7.59 7.58C7.22 7.95 7 8.45 7 9v10a2 2 0 0 0 2 2h9c.83 0 1.54-.5 1.84-1.22l3.02-7.05c.09-.23.14-.47.14-.73zM1 21h4V9H1z"/></svg>
          <p>{{ chat.likes }}</p>
          <svg @click="reaccionar(chat, 'dislike')" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M19 15h4V3h-4m-4 0H6c-.83 0-1.54.5-1.84 1.22l-3.02 7.05c-.09.23-.14.47-.14.73v2a2 2 0 0 0 2 2h6.31l-.95 4.57c-.02.1-.03.2-.03.31c0 .42.17.79.44 1.06L9.83 23l6.58-6.59c.37-.36.59-.86.59-1.41V5a2 2 0 0 0-2-2"/></svg>
          <p>{{ chat.dislikes }}</p>
        </div>

        <!-- Botón para mostrar el campo de respuesta -->
        <div class="flex justify-center gap-28 mt-4">
          <button @click="chat.mostrarResponder = true" class="bg-blue-500 rounded-sm text-white w-24 p-2 ">Responder</button>
          <p @click="eliminar(index)" class="text-red-500 cursor-pointer">Eliminar</p>
        </div>

        <!-- Formulario para agregar una respuesta -->
        <div v-if="chat.mostrarResponder" class="mt-4 bg-slate-300 w-[30rem] h-auto rounded-lg p-4">
          <div class="flex justify-around mt-4">
            <div class="text-start flex items-center gap-6">
              <img class="w-10 h-10 rounded-full" src="https://hips.hearstapps.com/hmg-prod/images/mh-celeb-name-changes-1567632828.png?crop=0.429xw:0.859xh;0.0321xw,0&resize=640:*" alt="">   
              <input class="border border-black w-[20rem] h-[5rem] p-2" type="text" v-model="respuesta">
            </div>
            <div>
              <button @click="insertar2(index)" class="bg-blue-500 rounded-sm text-white w-24 p-2">Enviar</button>
            </div>
          </div>
        </div>

        <!-- Mostrar respuesta -->
        <div v-if="chat.respuesta" class="mt-4 bg-slate-300 w-[30rem] h-auto rounded-lg p-4">
          <div class="flex justify-center gap-6">
            <img class="w-10 h-10 rounded-full" src="https://hips.hearstapps.com/hmg-prod/images/mh-celeb-name-changes-1567632828.png?crop=0.429xw:0.859xh;0.0321xw,0&resize=640:*" alt=""> 
            <h2>{{ chat.respuesta }}</h2>
          </div>
          <div class="flex justify-start ml-6 gap-4">
            <svg @click="reaccionar(chat, 'like')" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M23 10a2 2 0 0 0-2-2h-6.32l.96-4.57c.02-.1.03-.21.03-.32c0-.41-.17-.79-.44-1.06L14.17 1L7.59 7.58C7.22 7.95 7 8.45 7 9v10a2 2 0 0 0 2 2h9c.83 0 1.54-.5 1.84-1.22l3.02-7.05c.09-.23.14-.47.14-.73zM1 21h4V9H1z"/></svg>
            <p>{{ chat.likes }}</p>
            <svg @click="reaccionar(chat, 'dislike')" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M19 15h4V3h-4m-4 0H6c-.83 0-1.54.5-1.84 1.22l-3.02 7.05c-.09.23-.14.47-.14.73v2a2 2 0 0 0 2 2h6.31l-.95 4.57c-.02.1-.03.2-.03.31c0 .42.17.79.44 1.06L9.83 23l6.58-6.59c.37-.36.59-.86.59-1.41V5a2 2 0 0 0-2-2"/></svg>
            <p>{{ chat.dislikes }}</p>
          </div>

          <!-- Botón para mostrar el campo de respuesta secundaria -->
          <div class="flex justify-center mt-4">
            <button @click="chat.mostrarResponderSecundaria = true" class="bg-blue-500 rounded-sm text-white w-24 p-2">Responder</button>
          </div>

          <!-- Formulario para agregar una respuesta secundaria -->
          <div v-if="chat.mostrarResponderSecundaria" class="mt-4">
            <div class="flex justify-around mt-4">
              <div class="text-start flex items-center gap-6">
                <img class="w-10 h-10 rounded-full" src="https://hips.hearstapps.com/hmg-prod/images/mh-celeb-name-changes-1567632828.png?crop=0.429xw:0.859xh;0.0321xw,0&resize=640:*" alt="">   
                <input class="border border-black w-[20rem] h-[5rem] p-2" type="text" v-model="respuestaSecundaria">
              </div>
              <div>
                <button @click="insertarSecundaria(index)" class="bg-blue-500 rounded-sm text-white w-24 p-2">Enviar</button>
              </div>
            </div>
          </div>

          <!-- Mostrar respuestas secundarias -->
          <div v-for="(respuestaSecundaria, subIndex) in chat.respuestasSecundarias" :key="subIndex" class="mt-4 bg-slate-100 w-[28rem] h-auto rounded-lg p-4 ml-2 ">
            <div class="flex justify-center gap-6">
              <img class="w-10 h-10 rounded-full" src="https://hips.hearstapps.com/hmg-prod/images/mh-celeb-name-changes-1567632828.png?crop=0.429xw:0.859xh;0.0321xw,0&resize=640:*" alt=""> 
              <h2>{{ respuestaSecundaria.respuesta }}</h2>
            </div>
            <div class="flex justify-start ml-6 gap-4 mt-2">
              <svg @click="reaccionar(respuestaSecundaria, 'like')" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M23 10a2 2 0 0 0-2-2h-6.32l.96-4.57c.02-.1.03-.21.03-.32c0-.41-.17-.79-.44-1.06L14.17 1L7.59 7.58C7.22 7.95 7 8.45 7 9v10a2 2 0 0 0 2 2h9c.83 0 1.54-.5 1.84-1.22l3.02-7.05c.09-.23.14-.47.14-.73zM1 21h4V9H1z"/></svg>
              <p>{{ respuestaSecundaria.likes }}</p>
              <svg @click="reaccionar(respuestaSecundaria, 'dislike')" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M19 15h4V3h-4m-4 0H6c-.83 0-1.54.5-1.84 1.22l-3.02 7.05c-.09.23-.14.47-.14.73v2a2 2 0 0 0 2 2h6.31l-.95 4.57c-.02.1-.03.2-.03.31c0 .42.17.79.44 1.06L9.83 23l6.58-6.59c.37-.36.59-.86.59-1.41V5a2 2 0 0 0-2-2"/></svg>
              <p>{{ respuestaSecundaria.dislikes }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
