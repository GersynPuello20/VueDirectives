
<script setup>
import {ref} from 'vue'

const users = ["Pepe", "Ana", "Juana", "Lola"]

const isChecked = ref(true)
</script>

<template>
    <ul>
        <li v-for="(user, i) in users"  :key="i">{{ user }}</li>
    </ul>
    
    <input type="checkbox" id="check" v-model="isChecked"/> 
    <label for="check">Pínchame</label>
    <div class="bg-blue-400 text-white rounded py-1 px-2"
    :class="{'bg-orange-500' : isChecked}"
    >
        Este es un mensaje 
    </div>
    <div v-show="isChecked">
        Este es un mensaje que podría ocultar
    </div>
    <div v-if="false">
        Este es un mensaje que podría ocultar
    </div>
    <div v-else>
        Esto se ve porque no cumplió la condición del if 
    </div>
</template>