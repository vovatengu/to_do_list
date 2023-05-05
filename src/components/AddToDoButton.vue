<template>
    <div>
      <form @submit="addToDo">
        <input type="text" v-model="title" name="title">
        <button type="submit">Добавить</button>
      </form>
    </div>
  </template>

<script>

    export default {
    name: 'AddToDoButton',
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addToDo(event){
            event.preventDefault();
        
            const newToDoObject = {
                id: Math.random() * 9999, //uuid
                title: this.title
            }
            
            this.$emit("add-todo-event", newToDoObject);
            this.title= '';
        }
    }
}
</script>