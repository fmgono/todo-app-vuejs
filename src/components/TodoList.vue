<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => todo.done).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => !todo.done).length}}</p>
    <todo
      v-for="todo in todos"
      v-on:delete-todo="deleteTodo"
      v-on:complete-todo="completeTodo"
      v-bind:todo="todo"
      v-bind:key="todo.id"
    ></todo>
  </div>
</template>

<script>
import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    },
  },
};
</script>

<style>
</style>
