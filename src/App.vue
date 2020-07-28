<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
    <AddTodo v-on:add-todo="addTodo"/>
  </div>
</template>
<script>
  import Todos from './components/Todos';
  import AddTodo from './components/AddTodo';
  export default {
  name: 'app',
  components: {
  Todos,
  AddTodo
  },
  data() {
  return {
  todos: [
  {
  id: 1,
  title: 'Create Todo App Project',
  completed: false
  },
  {
  id: 2,
  title: 'Run the server & clean the project',
  completed: false
  },
  {
  id: 3,
  title: 'Create array to store data',
  completed: false
  },
  {
  i: 4,
  title: 'Create relevant components',
  completed: false
  },
  {
  i: 5,
  title: 'Display the todos',
  completed: false
  }
  ],
  }
  },
  methods: {
  addTodo(newTodoObj) {
  this.todos = [...this.todos, newTodoObj];
  },
  deleteTodo(todoId) {
  this.todos = this.todos.filter(todo => todo.id !== todoId);
  }
  }
  }
</script>
<style>
</style>