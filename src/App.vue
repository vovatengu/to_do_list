<template>
  <div id="app">
    <h1>To-Do-List</h1>
    <AddToDoButton @add-todo-event="addToDoItem" />
    <ToDos v-bind:todoEntries="todoEntries" @delete-todo-event="deleteToDoItem" />
  </div>
</template>

<script>
import AddToDoButton from './components/AddToDoButton.vue'
import ToDos from './components/ToDos.vue'
export default {
  name: 'App',
  components: {
    ToDos,
    AddToDoButton
  },
  data() {
    return {
      todoEntries: []
    }
  },
  methods: {
    addToDoItem(newToDoItem) {
      // this.todoEntries = [...this.todoEntries, newToDoItem]
      this.todoEntries.push(newToDoItem)
    },
    deleteToDoItem(toDoId) {
      this.todoEntries = this.todoEntries.filter((todo) => todo.id !== toDoId)
    }
  }
}
</script>

<style></style>

