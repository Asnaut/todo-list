<!--  -->
<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        v-model="title"
        name="title"
        placeholder="Add Todo..."
      />
      <input type="submit" value="Add" class="btn" />
    </form>
  </div>
</template>

<script>
import uuid from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },

  components: {},

  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: uuid.v4(),
        title: this.title,
        completed: false
      };
      this.$emit("add-todo", newTodo);
      // clear the placeholder
      this.title = "";
    }
  }
};
</script>
<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 8px;
}
input[type="submit"] {
  flex: 2;
}
</style>
