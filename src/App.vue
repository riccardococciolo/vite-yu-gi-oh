<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';


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
        this.store.cards = resp.data.data;
    });
  },
  components: { 
    AppHeader, CardsList,
  },
}

</script>

<template>
  <AppHeader />
  <CardsList />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>
