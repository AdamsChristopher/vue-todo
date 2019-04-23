<template>
  <div>
    <form v-on:submit="addTodo">
      <input 
        type="text" 
        name="title" 
        placeholder="Add Todo..."
        v-model="title"
      >
      <input 
        class="button" 
        type="submit" 
        value="Sublit"
      >
    </form>
  </div>
</template>

<script>
// import uuid from 'uuid';

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(event) {
      event.preventDefault();
      const newTodo = {
        // id: uuid.v4(),
        title: this.title,
        completed: false
      }
      this.$emit('add-todo', newTodo);
      this.title = '';
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
  flex: 2;
}
</style>
