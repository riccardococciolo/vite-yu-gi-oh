<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';
import CardsFilter from "./components/CardsFilter.vue";


export default {
  data() {
    return {
      store,
    };
  },
  created() {
    this.store.loading = true
    axios
      .get(this.store.apiCards,)
      .then((resp) => {
        this.store.cards = resp.data.data;
        this.store.loading = false;
      });
  },
  methods: {
    handleSelected() {
      if (this.store.selectedOption !== "home") {
        this.store.loading = true
        axios
          .get(this.store.apiCards, {
            params: {
              archetype: this.store.selectedOption,
            },
          })
          .then((resp) => {
            this.store.cards = resp.data.data;
            this.store.loading = false;
          });
      } else {
        this.store.loading = true
        axios
          .get(this.store.apiCards,)
          .then((resp) => {
            this.store.cards = resp.data.data;
            this.store.loading = false;
          });
      }
    },
  },
  components: {
    AppHeader,
    CardsList,
    CardsFilter
  },
}

</script>

<template>
  <AppHeader />
  <main class="wrapper p-5">
    <CardsFilter @selected="handleSelected" />
    <CardsList />
  </main>
</template>

<style lang="scss">
@use "./style/general.scss";
@use "./style/partials/variables" as *;

.wrapper {
  background-color: $primary;
}
</style>
