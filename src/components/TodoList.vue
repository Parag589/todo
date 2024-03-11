<template>
  <div>
    <h2>Todo List</h2>
    <ul>
      <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" @deleteTodo="deleteTodo" />
    </ul>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";

export default {
  props: {
    todos: Array,
  },
  components: {
    TodoItem,
  },
  methods: {
    deleteTodo(id) {
      this.$emit("deleteTodo", id);
    },
  },
};
</script>
