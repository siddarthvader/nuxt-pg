<template>
  <div class="container">
    <div>
      <header />
    </div>
  </div>
</template>

<script>
import Header from "~/components/Header.vue";

export default {
  head() {
    return {
      title: "trying nuxt",
      meta: [{ hid: "desc", name: "desc", content: "jokes are coming" }]
    };
  },
  components: {
    Header
  }
};
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
