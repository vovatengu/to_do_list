// ToDos.vue
<template>
  <div>
      <ul>
          <li v-bind:key="item.id" v-for="item in todoEntries">
              <ToDoItem v-bind:todoItem="item" @delete-todo-event="$emit('delete-todo-event', item.id)"/>
          </li>   
      </ul>
  </div>
</template>

<script>
import ToDoItem from "./ToDoItem";

export default {
  name: 'ToDos',
  components: {
      ToDoItem
  },
  props: [
      "todoEntries"
  ]
}
</script>

<style>
li {
  list-style-type: none;
  }
ul {
  padding-left: 0;}
</style>