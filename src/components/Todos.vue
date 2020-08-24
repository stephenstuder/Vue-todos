<!-- <template>
  <div>
    <div v-for="todo in todos" v-bind:key="todo.id">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template> -->
<template>
  <v-row align="center">
    <v-card class="mx-auto" width="800" outlined>
      <v-subheader>TODO LIST</v-subheader>
      <v-list class="list-group">
        <v-slide-y-transition class="py-0" group tag="v-list">
          <TodoItem
            class="list-group-item px-2 py-3"
            v-for="(todo, i) in todos"
            :key="i"
            v-bind:todo="todo"
            v-on:del-todo="$emit('del-todo', todo.id)"
          />
        </v-slide-y-transition>
      </v-list>
    </v-card>
  </v-row>
</template>
<script>
import TodoItem from "./TodoItem.vue";
export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: ["todos"],
};
</script>

<style>
</style>
