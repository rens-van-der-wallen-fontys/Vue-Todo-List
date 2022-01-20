<template>
 <h1>My todo list</h1>
 <TodoList v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
 <NewTodo v-on:new-todo="addTodo"/>
</template>

<script>
import TodoList from './components/TodoList.vue'
import todos from './todos.json'
import NewTodo from './components/NewTodo.vue'

export default {
  name: 'App',
  data() {
    return {
      todos: todos
    }
  },

  components: {
    TodoList,
    NewTodo
  },

  methods: {
    addTodo(todoItem) {
      this.todos.push(todoItem)
    },

    deleteTodo (id) {
      this.todos = this.todos.filter(todo => todo.id!==id)
    }
  }

}
</script>

<style>

</style>
