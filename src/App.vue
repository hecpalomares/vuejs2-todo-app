<template>
  <div>
    <todo-list v-bind:todos="todos"></todo-list>
  </div>
</template>

<script>
import TodoList from './components/TodoList';

export default {
  name: 'app',
  components: {
    TodoList,
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
