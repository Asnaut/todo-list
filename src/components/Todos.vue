<!--  -->
<template>
  <div>
    <div :key="todo.id" v-for="todo in todos">
      <TodoItem :todo="todo" @del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  data() {
    return {};
  },
  name: "Todos",
  props: ["todos"],
  components: {
    TodoItem
  },

  computed: {},

  methods: {}
};
</script>
<style lang="scss" scoped></style>
