<template>
  <div id="app">
    <div class="appli-title"><h1>VueList</h1></div>
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create-todo="createTodo"></create-todo>
  </div>
</template>

<script>
import swal from 'sweetalert'
import TodoList from '@/components/TodoList'
import CreateTodo from '@/components/CreateTodo'

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo
  },
  data () {
    return {
      todos: [{
        title: 'Todo',
        project: '詳細',
        done: false
      }, {
        title: 'Todo',
        project: '詳細',
        done: false
      }, {
        title: 'Todo',
        project: '詳細',
        done: false
      }, {
        title: 'Todo',
        project: '詳細',
        done: false
      }]
    }
  },
  methods: {
    createTodo (newTodo) {
      this.todos.push(newTodo)
      swal('Success!', '完了!', 'success')
    }
  }
}
</script>
<style>
 @import '../style.css'
</style>
