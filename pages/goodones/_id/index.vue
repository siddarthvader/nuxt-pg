<template>
  <!-- <div>single joke {{$route.params.id}}</div> -->
  <Joke :joke="joke.joke" :id="joke.id"></Joke>
</template>

<script>
import Joke from "../../../components/Joke";
import axios from "axios";
export default {
  components: { Joke },
  head() {
    return {
      title: this.joke,
      meta: [{ hid: "desc", name: "desc", content: "jokes are coming" }]
    };
  },
  data() {
    return {
      joke: {}
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios(
        "https://icanhazdadjoke.com/j/" + this.$route.params.id,
        config
      );
      console.log(res.data);
      this.joke = res.data;
    } catch (err) {
      console.log(err);
    }
  }
};
</script>

<style lang="scss" scoped>
</style>