<script setup lang="ts">
import { ref } from 'vue';
import { Todo } from './models/Todo';

const state = ref<Todo>({name: "", done: false, level: 0})

function handleClick(){
  console.log("Klickat på knappen ==> " +state.value.name, state.value.level, state.value.done);
}

</script>

<template>

<input type="text" v-model="state.name" />
<input type="checkbox" v-model="state.done" />
<input type="number" v-model="state.level" />

<button @click="handleClick">KLICK</button>

<p>{{ state.name }} - {{ state.level }} - {{ state.done }}</p> 

</template>

<style scoped>

</style>
