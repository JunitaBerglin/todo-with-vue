<script setup lang="ts">
import { ref } from 'vue';
import { Todo } from '../models/Todo';
import CreateTodo from './CreateTodo.vue';
import ShowTodos from './ShowTodos.vue';

// FÖRÄLDER TILL SHOWTODO

const todos = ref<Todo[]>([new Todo('Test', true, 4)]);

function addNewTodo(t: Todo) {
    console.log(t);
    todos.value.push(t);
}


const toggleTodo = (i: number) => {
    todos.value[i].done = !todos.value[i].done
}

</script>

<template>
<CreateTodo @create-new-todo="addNewTodo"></CreateTodo>
<ShowTodos :todo="todo" v-for="(todo, index) in todos" :key="index" @toggle-todo="()=> toggleTodo(index)"></ShowTodos>

</template>

<style scoped>

</style>