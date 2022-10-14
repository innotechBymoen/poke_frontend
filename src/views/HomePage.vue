<template>
  <div>
    <post-pokemon></post-pokemon>
    <all-pokemon></all-pokemon>
  </div>
</template>

<script>
import AllPokemon from "@/components/AllPokemon.vue";
import PostPokemon from "@/components/PostPokemon.vue";
export default {
  components: {
    AllPokemon,
    PostPokemon,
  },
};
</script>

<style scoped>
</style>