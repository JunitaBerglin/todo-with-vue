<script setup lang="ts">
import { ref } from 'vue';
import { Todo } from '../models/Todo';

const newTodo = ref<Todo>({name:"", done: false, level: 0})
const emit = defineEmits(["createNewTodo"]);

function handleClick(){ 
  console.log(newTodo.value);
  emit("createNewTodo", { ...newTodo.value })

  newTodo.value = {name: "", done: false, level: 0 };
}

function emptyInputs(t: Todo){
    t = {name: "", done: false, level: 0 };
}

</script>

<template>
<h1>Vad behöver du göra?</h1>
<form @submit.prevent="handleClick">
<input type="text" v-model="newTodo.name" placeholder="skriv din uppgift" />
<input type="number" v-model="newTodo.level" min="0" max="5"/>
<input type="checkbox" v-model="newTodo.done" />
<button>SPARA</button>
</form>
</template>

<style scoped>


</style>