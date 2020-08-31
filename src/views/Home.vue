<template>
  <div id="app" class="d-flex flex-column justify-around bg-grey">
    <Header />
    <v-container class>
      <v-row>
        <v-col cols="12">
          <AddTodo v-on:add-todo="addTodo" />
          <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import Todos from "../components/Todos";
import AddTodo from "../components/AddTodo";
import axios from "axios";
export default {
  name: "Home",
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    deleteTodo(id) {
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then((res) => {
          return (
            (this.todos = this.todos.filter((todo) => todo.id !== id)), res
          );
        })
        /* eslint no-console: ["error", { allow: ["warn", "error"] }] */
        .catch((err) => console.error(err));
    },
    addTodo(newTodo) {
      const { title, completed } = newTodo;
      axios
        .post("https://jsonplaceholder.typicode.com/todos", {
          title,
          completed,
        })
        .then((res) => (this.todos = [...this.todos, res.data]))
        /* eslint no-console: ["error", { allow: ["warn", "error"] }] */
        .catch((err) => console.error(err));
    },
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=5")
      .then((res) => (this.todos = res.data))
      /* eslint no-console: ["error", { allow: ["warn", "error"] }] */
      .catch((err) => console.error(err));
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.bg-grey {
  background-color: #343434;
  min-height: 100vh;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>