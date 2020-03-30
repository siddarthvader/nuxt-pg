<template>
  <div class="max-w-sm mx-auto flex p-6 bg-white rounded-lg shadow-xl m-2">
    <div class="flex-shrink-0"></div>
    <div class="ml-6 pt-1">
      <nuxt-link :to="'goodones/'+id">
        <h4 class="text-xl text-gray-900 leading-tight">{{id}}</h4>
        <p class="text-base text-gray-600 leading-normal">{{joke}}</p>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Joke",
  props: ["joke", "id"]
};
</script>

<style lang="scss" scoped>
</style>