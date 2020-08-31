<template>
  <v-row align="center">
    <v-card class="mx-auto my-4 px-3" min-width="600" outlined>
      <form class="d-flex align-center" @submit="addTodo">
        <v-text-field class="mr-3" v-model="title" :counter="50" label="Add Todo..." required></v-text-field>
        <v-btn type="submit" value="submit" class="ml-2 primary">Add Todo</v-btn>
      </form>
    </v-card>
  </v-row>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false,
      };
      //send up to parent
      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>

<style scoped>
</style>