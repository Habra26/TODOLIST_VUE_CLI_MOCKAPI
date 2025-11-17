<script setup>
import { reactive, onMounted } from "vue";
import DB from "@/services/DB";
import Todo from "./Todo.vue";
import TodoListAddForm from "./TodoListAddForm.vue";
import TodolistFooter from "./TodolistFooter.vue";

const todos = reactive([]);

onMounted(async () => {
  DB.setApiURL("https://68e117c793207c4b47963bf2.mockapi.io/");
  todos.splice(todos.length, 0, ...(await DB.findAll()));
  console.table(todos);
});
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
    <ul class="m-4 divide-y divide-slate-200 text-slate-600" role="list" aria-label="Todos">
      <!-- ITEM (exemple) -->
      <Todo v-for="todo in todos" :key="todo.id" :todo="todo" />
    </ul>

    <!-- FOOTER DE LISTE -->
    <TodolistFooter />
  </section>
</template>

<style scoped></style>
