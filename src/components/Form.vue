<template>
  <div>
    <input
      @click="clearText"
      v-model="todoText"
      placeholder="Todo text"
      type="text"
      name="add-todo"
    />
    <button
      @click="() => {
            $emit('add-todo', todoText);
            clearText();
        }"
    >Add</button>
  </div>
</template>


<script>
export default {
  name: "Form",
  data() {
    return {
      todoText: ""
    };
  },
  methods: {
    clearText() {
      this.todoText = "";
    }
  }
};
</script>

<style scoped>
div {
  margin: 40px;
}
</style>
