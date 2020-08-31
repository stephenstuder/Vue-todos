<template>
  <div class="about bg-grey d-flex align-center flex-column">
    <br />
    <h1>About This Project</h1>
    <div class="content">
      <br />
      <p>This started out as my first Vue project ever had a very plain style as shown below</p>
      <br />
      <br />
      <v-img :src="image" alt="screenshot" class="img" />
      <br />
      <br />
      <p>I have used this as an example app to learn Vuetify, transitions, and will eventually create a Deno backend to support it. Some ambitions down the pipline including login, statistics, dates, etc. I am not trying to create a groundbreaking new app, i just want to showcase what i can build.</p>
    </div>
  </div>
</template>
<script>
import image from "../assets/vue-screenshot.png";
export default {
  data: function () {
    return {
      image: image,
    };
  },
};
</script>
<style>
.bg-grey {
  background-color: #343434;
  color: #fff;
  min-height: 100vh;
}
.content {
  width: 700px;
}
</style>
© 2020 GitHub, Inc.