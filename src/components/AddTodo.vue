<template>
  <div>
    <h2>Add Todo</h2>
    <input v-model="newTodo" placeholder="Enter todo text" />
    <button @click="addTodo">Add Todo</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: "",
    };
  },
  methods: {
    addTodo() {
      this.$emit("addTodo", this.newTodo);
      this.newTodo = "";
    },
  },
};
</script>
