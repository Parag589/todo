<template>
  <li>
    {{ todo.text }}
    <button @click="deleteItem">Delete</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: Object,
  },
  methods: {
    deleteItem() {
      this.$emit("deleteItem", this.todo.id);
    },
  },
};
</script>
