<template>
  <div>
    <AddTodo @addTodo="addTodo" />
    <TodoList :todos="todos" @deleteTodo="deleteTodo" />
  </div>
</template>

<script>
import AddTodo from "../components/AddTodo.vue";
import TodoList from "../components/TodoList.vue";


export default {
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    addTodo(newTodo) {
      const todo = { id: Date.now(), text: newTodo };
      this.todos.push(todo);
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
  components: {
    AddTodo,
    TodoList,
  },
};
</script>
