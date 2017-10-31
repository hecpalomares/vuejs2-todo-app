<template>
  <div id="app">
    <h1 class="ui dividing centered header">Vue.js Todo App</h1>
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create-todo="createTodo"></create-todo>
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'app',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [{
        title: 'Finish S-237234',
        project: 'Project A',
        done: false,
      }, {
        title: 'Talk with RH about dental care',
        project: 'Project B',
        done: true,
      }, {
        title: 'Finish tutorial on scotch.io',
        project: 'Project C',
        done: false,
      }],
    };
  },
  methods: {
    createTodo(newTodo) {
      this.todos.push(newTodo);
    },
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
