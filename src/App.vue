<template>
  <v-app>
    <v-app-bar app color="dark" dark>
      <div id="nav" class="d-flex align-center">
        <h1>Vue + Deno Todo's</h1>
        <v-btn text small class="ml-3" to="/">Home</v-btn>
        <v-btn text small to="/about">About</v-btn>
      </div>
      <v-spacer></v-spacer>

      <v-btn href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank" text>
        <span class="mr-2">In Progress..</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
