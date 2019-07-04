<template>
  <li
    @click="handleClick"
    v-bind:class="{'is-completed': todo.completed, 'is-not-completed': !todo.completed}"
  >
    <p>{{todo.completed ? "✔" : "✖" }} - {{todo.text}}</p>
    <button @click="$emit('del-todo', todo.id)">X</button>
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    handleClick() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.is-completed {
  color: green;
}

.is-not-completed {
  color: red;
}

li {
  display: flex;
  justify-content: space-between;
  font-size: 1.2rem;
  text-align: left;
  width: 100%;
}

p {
  margin: 0;
}

button {
  margin: auto 0;
  padding: 0;
  height: 1.3rem;
  width: 1.3rem;
  border-radius: 50%;
  color: white;
  background-color: red;
}
</style>