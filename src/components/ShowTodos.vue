<script setup lang="ts">
import { ref } from 'vue';
import { Todo } from '../models/Todo';

// BARNET TILL TODOLIST

interface IShowTodoProps {
    todo: Todo;
}

defineProps<IShowTodoProps>();

defineEmits(["toggleTodo"]);

</script>

<template>

<li  @click="$emit('toggleTodo')" class="todo" :class="{done: todo.done, important: todo.level > 3}">{{ todo.name }}</li>

</template>

<style scoped>

ul{
    list-style: none;
    display: flex;
    flex-direction: column;
}
.important{
  background-color: red;
}

.lessImportant{
  background-color: yellow;
}

.todo{
text-decoration: underline;
}

.todo.done{
text-decoration: line-through;
}

</style>
