<template>
    <form @submit="newTodo">
        <input type="text" v-model="title" name="title" />

        <button type="submit" @click="newTodo">Add</button>
    </form>
</template>

<script>
import uuid from 'uuid'
export default {
  name: 'NewTodo',
  data() {
      return {
          title: ''
      }
  },
    methods: {
        newTodo (theEvent) {
            theEvent.preventDefault();
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }

            this.$emit('new-todo', newTodo)
            this.title = ''
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
