<script>
import axios from "axios";
import { store } from "./store.js";

export default {
  data() {
    return {
      store,
    };
  },
  created() {
    axios
      .get(this.store.apiCards)
      .then((resp) => {
        this.store.cards = resp.data;
    });
  },
  components: {},
}

</script>

<template>

</template>

<style lang="scss">
@use "./style/general.scss";
</style>
