<template>
  <div>
    <button @click="get_pokemon">GET POKEMON</button>
    <div v-for="(pokemon, index) in pokemons" :key="index">
      <h2>{{ pokemon[0] }}</h2>
      <img :src="pokemon[2]" />
      <p>{{ pokemon[1] }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      pokemons: [],
    };
  },

  methods: {
    get_pokemon() {
      axios
        .request({
          url: `${process.env.VUE_APP_BASE_DOMAIN}/api/pokemon`,
        })
        .then((res) => {
          this.pokemons = res[`data`];
        })
        .catch((err) => {
          err;
        });
    },
  },
};
</script>

<style scoped>
</style>