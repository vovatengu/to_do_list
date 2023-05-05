<template>
  <div >
    <p >{{ todoItem.title }}<input type="checkbox">
    <button @click="$emit('delete-todo-event', todoItem.id)">Удалить</button>
    </p>
  </div>
</template>

<script>

export default {
  name: 'ToDoItem',
  components: {
  },props: [
    "todoItem"
  ],

}
</script>
