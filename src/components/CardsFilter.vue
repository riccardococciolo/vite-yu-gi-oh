<script>
import { store } from '../store'

export default {
 data() {
    return {
        store,
        selected: "",
    }
 },
}

console.log(store);
</script>

<template>
    <div>
        <select class="form-select w-25" aria-label="Default select example" @change="$emit('selected')" v-model="store.selectedOption">
            <option selected>home</option>
            <option value="alien">Alien</option>
            <option value="Ally of Justice">Ally of Justice</option>
            <option value="Ancient Gear">Ancient Gear</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>

</style>