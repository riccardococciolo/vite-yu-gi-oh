<script>
import { store } from '../store';
import card from './card.vue';
 
export default {
    data() {
        return {
            store,
        }
    },
    components: {card},
}
</script>

<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="col" v-for="(card) in store.cards">
                    <card :card="card" />
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use "../style/partials/variables" as *;


</style>