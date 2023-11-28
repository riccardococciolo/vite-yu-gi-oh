<script>
export default {
      props: {
        character: Object
      }
};
</script>

<template>
    <div class="h-100">
        <div class="card h-100">
            <img :src="character.card_images[0].image_url" class="card-img-top" alt="">
            <div class="card-body wrapper">
                <p class="card-title text-white fw-bolder text-center" >{{ character.name }}</p>
                <p class="card-text text-center">{{ character.archetype }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.card {
    border-radius: 0; // Rimuove l'arrotondamento dei bordi
}

.wrapper {
    background-color: $primary;
}
</style>