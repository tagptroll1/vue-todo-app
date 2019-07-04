<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    <Form v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import Form from "./components/Form.vue";

export default {
  name: "app",
  components: {
    Todos,
    Form
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(text) {
      const id = Math.max(...this.todos.map(todo => todo.id)) + 1;
      this.todos.push({ id, text, completed: false });
    }
  },
  data() {
    return {
      todos: [
        { id: 1, text: "First todo", completed: false },
        { id: 2, text: "Second todo", completed: true }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
