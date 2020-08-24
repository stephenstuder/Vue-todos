<template>
  <v-card class="mx-auto my-4 px-3" width="800" outlined>
    <form class="d-flex align-center" @submit="addTodo">
      <v-text-field
        class="mr-3"
        v-model="title"
        :counter="50"
        :error-messages="errors"
        label="Add Todo..."
        required
      ></v-text-field>
      <v-btn type="submit" value="submit" class="mr-4 primary">submit</v-btn>
    </form>
  </v-card>
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