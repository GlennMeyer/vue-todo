<template>
  <div>
    <p>Completed Tasks: {{ todos.filter(todo => todo.done).length }}</p>
    <p>Pending Tasks: {{ todos.filter(todo => !todo.done).length }}</p>
    <todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo" :key="todo.id"></todo>
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
      const todoindex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    }
  }
}
</script>

<style>

</style>
