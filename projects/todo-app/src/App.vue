<template>
  <div id="app">
    <create-todo v-on:add-todo="addTodo" />
    <todo-list v-bind:todos="todos"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import CreateTodo from './components/CreateTodo.vue'
export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
  data () {
    return {
      todos: [
        {
          title: 'To do A',
          project: 'Project A',
          done: true
        },
        {
          title: 'To do B',
          project: 'Project B',
          done: false
        },
        {
          title: 'To do C',
          project: 'Project C',
          done: false
        },
        {
          title: 'To do D',
          project: 'Project D',
          done: false
        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
