<script setup>
import Todo from './Todo.vue';
import TodoListAddForm from './TodoListAddForm.vue';
import TodolistFooter from './TodolistFooter.vue';


</script>

<template>
  <section
    class="bg-slate-100 rounded-xl shadow ring-1 ring-slate-200/60 overflow-hidden"
    aria-labelledby="todo-heading"
  >
    <h2 id="todo-heading" class="sr-only">Todo list</h2>

    <!-- INPUT PRINCIPAL -->
    <TodoListAddForm />

    <!-- LISTE DES TODOS -->
    <ul class="m-4 divide-y divide-slate-200" role="list" aria-label="Todos">
      <!-- ITEM (exemple) -->
      <Todo />
    </ul>

    <!-- FOOTER DE LISTE -->
    <TodolistFooter />
  </section>
</template>

<style scoped></style>
