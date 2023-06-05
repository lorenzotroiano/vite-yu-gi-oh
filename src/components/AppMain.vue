<script >
import { store } from './../store.js';

import Card from './Card.vue';

export default {
    name: "AppMain",

    components: {
        Card
    },
    data() {
        return {
            store,
        }
    }
}

</script>

<template>
    <main>

        <section>
            <select name="cards" id="cards">
                <option value="alien">Alien</option>
                <option value="zombie">Zombie</option>
                <option value="human">Human</option>
                <option value="hello">Hello</option>
            </select>
        </section>


        <Card v-for="card in store.cardList" />
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

main {
    background-color: $colorePrimario;
    min-height: 500px;
    padding: 20px;

    section {
        width: 90%;
        margin: 0 auto;
    }


}
</style>
