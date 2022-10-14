<template>
  <div>
    <input type="text" placeholder="Name" ref="name_input" />
    <input type="text" placeholder="Description" ref="desc_input" />
    <input type="text" placeholder="Image URL" ref="img_input" />
    <button @click="post_pokemon">Submit</button>
    <h5>{{ status }}</h5>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      status: "",
    };
  },
  methods: {
    post_pokemon() {
      axios
        .request({
          url: `${process.env.VUE_APP_BASE_DOMAIN}/api/pokemon`,
          method: "POST",
          data: {
            name: this.$refs[`name_input`][`value`],
            image_url: this.$refs[`img_input`][`value`],
            description: this.$refs[`desc_input`][`value`],
          },
        })
        .then(() => {
          this.status = "Success";
        })
        .catch(() => {
          this.status = "Something went wrong!";
        });
    },
  },
};
</script>

<style scoped>
</style>