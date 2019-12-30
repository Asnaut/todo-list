<template>
  <div id="app">
    <Todos :todos="todos" @del-todo="deleteTodo"></Todos>
    <AddTodo @add-todo="addTodo"></AddTodo>
  </div>
</template>

<script>
import Todos from "../components/Todos";
import AddTodo from "../components/AddTodo";
import Cookies from "js-cookie";
export default {
  name: "Home",
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: []
    };
  },
  mounted() {
    // turn string to json
    // cookies stores in the string format
    this.todos = JSON.parse(Cookies.get("todos"));
    window.console.log(this.todos);
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
      const todoStr = JSON.stringify(this.todos);
      Cookies.set("todos", todoStr, { expires: 14 });
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
      const todoStr = JSON.stringify(this.todos);
      Cookies.set("todos", todoStr, { expires: 14 });
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: azure;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
