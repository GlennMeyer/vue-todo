<template>
  <div id="app">
    <todo-list v-bind:todos="todos"></todo-list>
  </div>
</template>

<script>
import TodoList from './components/TodoList'

export default {
  name: 'app',
  components: {
    TodoList,
  },
  data() {
    return {
      todos: [{
        id: 0,
        title: 'Todo A',
        project: 'Project A',
        done: false,
      },{
        id: 1,
        title: 'Todo B',
        project: 'Project B',
        done: true,
      },{
        id: 2,
        title: 'Todo C',
        project: 'Project C',
        done: false,
      },{
        id: 3,
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
