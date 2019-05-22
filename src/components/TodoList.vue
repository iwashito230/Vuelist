<template>
  <div>
    <p class="tasks">完了したタスク: {{ todos.filter(todo => { return todo.done === true }).length }}</p>
    <p class="tasks">未完了のタスク: {{ todos.filter(todo => { return todo.done === false }).length}}</p>
    <todo @delete-todo="deleteTodo" @complete-todo="completeTodo" v-for="todo in todos" :todo="todo"></todo>
  </div>
</template>

<script>
import Todo from './Todo'
import swal from 'sweetalert'

export default {
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    deleteTodo(todo) {
      swal({
        title: '削除しますか?',
	text: 'このTodoを完全に削除します!',
	icon: 'warning',
	buttons: true,
	dangerMode: true,
      })
      .then((willDelete) => {
        if (willDelete) {
	  const todoIndex = this.todos.indexOf(todo);
	  this.todos.splice(todoIndex, 1);
	  swal('Delete!', '削除しました', 'success')
	}
      });
    },
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos[todoIndex].done = true
      swal('Success!', '完了!', 'success')
    }
  }
}
</script>

<style>
 @import '../../style.css'
</style>
