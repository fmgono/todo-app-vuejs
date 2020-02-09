<template>
  <div id="app">
    <create-todo v-on:create-todo="addTodo"></create-todo>
    <todo-list v-bind:todos="todos"></todo-list>
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo,
  },
  // data function avails data to the template
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Todo A',
          project: 'Project A',
          done: false,
        },
        {
          id: 2,
          title: 'Todo B',
          project: 'Project B',
          done: false,
        },
        {
          id: 3,
          title: 'Todo C',
          project: 'Project C',
          done: true,
        },
      ],
    };
  },
  methods: {
    addTodo(data) {
      this.todos.push(data);
    },
  },
};
</script>

<style>
</style>
