<template>
  <v-top-navigation class="header">
    <h1>TodoList</h1>
    <div id="nav">
      <v-btn text small to="/">Home</v-btn>
      <v-btn text small to="/about">About</v-btn>
    </div>
  </v-top-navigation>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.header {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 10px;
}
.header a {
  color: #fff;
  padding-right: 5px;
  text-decoration: none;
}
</style>