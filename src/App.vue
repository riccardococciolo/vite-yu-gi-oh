<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from './components/AppHeader.vue'

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
  components: { AppHeader},
}

</script>

<template>
  <AppHeader />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>
