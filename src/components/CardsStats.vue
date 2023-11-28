<script>
import { store } from '../store';

export default {
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div class="bg-black w-100 p-2">
        <h3 class="text-white">Found {{ store.cards.length }} cards</h3>
    </div>
</template>

<style lang="scss" scoped>
 
</style>