<template>
  <div>
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"></Joke>
  </div>
  <!-- <div v-bind:for="joke in jokes">{{joke.joke}}</div> -->
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke";
export default {
  components: { Joke },
  head() {
    return {
      title: "good ones nuxt",
      meta: [{ hid: "desc", name: "desc", content: "jokes are coming" }]
    };
  },
  data() {
    return {
      jokes: []
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios("https://icanhazdadjoke.com/search", config);
      console.log(res.data);
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
  }
};
</script>

<style lang="scss" scoped>
</style>