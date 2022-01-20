<template>
  <li>
    <span> {{ todo.title }} </span>
    <button @click="$emit('delete-todo', todo.id)">Delete</button>
   </li>
</template>

<script>
export default {
  name: 'Todo',
  props: ['todo']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 li {
     list-style: none;
 }
 span {
    display: inline-block;
    min-width: 200px;
 }
</style>
