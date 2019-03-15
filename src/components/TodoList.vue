<template>
  <div>
    <p>Completed Tasks: {{ todos.filter(todo => todo.done).length }}</p>
    <p>Pending Tasks: {{ todos.filter(todo => !todo.done).length }}</p>
    <todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo" v-for="todo in todos" :todo.sync="todo" :key="todo.id"></todo>
  </div>
</template>

<script>
import Todo from './Todo'

export default {
  components: {
    Todo,
  },
  props: ['todos'],
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    },
  }
}
</script>

<style>

</style>
