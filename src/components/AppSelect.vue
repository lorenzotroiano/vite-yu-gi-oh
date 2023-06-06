<script >
import { store } from './../store.js';



export default {
    name: "AppSelect",

    data() {
        return {
            store,
        }
    }


}

</script>

<template>
    <section>
        <select name="cards" id="cards">
            <option v-for="option in store.optionList" value="alien">{{ option.archetype }}</option>

        </select>
    </section>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;



section {
    width: 90%;
    margin: 0 auto;
}
</style>