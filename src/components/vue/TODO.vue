<script setup>
import {ref} from 'vue'


const todos = ref([])

const todo = ref()

function add(){
    todos.value.unshift(todo.value)
    todo.value
}
</script>

<template>
    <div class="rounded shadow bg-slate-300 max-w-96 mx-auto mt-10 py-6 px-5">
        <div>
            <input v-model="todo" class="w-4/5 outline-none rounded px-2" placeholder="Edit me">
            <button 
            @click="add"
            class="w-1/5 bg-green-400 text-white text-center "
            >
                Añadir
            </button>
        </div>
        <div class="mt-4">
            <div v-for="(todo,i) in todos"
            :key="i"
            class="bg-amber-400 rounded px-2 mt-1"
            >
                {{todo}}
            </div>
        </div>
    </div>
</template>