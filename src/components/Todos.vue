<template>
  <ul>
    <TodoItem
      v-on:del-todo="$emit('del-todo', todo.id)"
      v-bind:todo="todo"
      v-for="todo in todos"
      v-bind:key="todo.id"
    />
  </ul>
</template>


<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "Todos",
  props: ["todos"],
  components: {
    TodoItem
  }
};
</script>

<style scoped>
ul {
  list-style: none;
  width: 20%;
  margin: 0 auto;
  padding: 10px;

  background-color: lightblue;
  box-shadow: 2px 2px 4px black;
}
</style>



