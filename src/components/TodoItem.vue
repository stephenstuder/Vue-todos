<template>
  <v-list-item-content class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <v-list-item-title class="p-3">
      <input type="checkbox" v-on:change="markComplete" />
      {{todo.title}}
      <button @click="$emit('del-todo', todo.id)" class="del">
        <i class="fa fa-trash" aria-hidden="true"></i>
      </button>
    </v-list-item-title>
  </v-list-item-content>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scope>
.todo-item {
  padding: 10px;
  width: 100%;
  border-bottom: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
}
.del {
  color: #000;
  border: none;
  padding: 5px 9px;
  cursor: pointer;
  float: right;
}
</style>