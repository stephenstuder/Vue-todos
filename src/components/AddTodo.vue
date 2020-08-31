<template>
  <v-row justify="center">
    <v-card class="my-4 px-3 py-3" width="503px" outlined>
      <form class="d-flex justify-center flex-column" @submit="addTodo">
        <v-text-field class v-model="title" :counter="50" label="Add Todo..." required></v-text-field>
        <v-btn type="submit" value="submit" width="100%" class="primary">Add Todo</v-btn>
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