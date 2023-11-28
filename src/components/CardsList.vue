<script>
import { store } from '../store';
import CardsStats from './CardsStats.vue';
import CharacterCard from './CharacterCard.vue';

export default {
    data() {
        return {
            store,
        }
    },
    components: { CharacterCard, CharacterCard, CardsStats },
}
</script>

<template>
    <div>
        <div class="container p-4">
            <div class="bg-white p-4">
                <CardsStats />
                <div class="row row-cols-5 g-4">
                    <div class="col" v-for="character in store.cards" :key="character.id">
                        <CharacterCard :character="character" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
</style>