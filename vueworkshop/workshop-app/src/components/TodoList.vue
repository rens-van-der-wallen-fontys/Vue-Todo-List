<template>
<div>
  <ul> 
     <Todo v-for="todo in todos" :key="todo.id" v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)"/>
  </ul>
</div>
</template>

<script>
import Todo from './Todo.vue'
export default {
  name: 'TodoList',
  props: ['todos'],
  components: {
    Todo
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 ul {
   padding-left: 0;
 }
</style>
