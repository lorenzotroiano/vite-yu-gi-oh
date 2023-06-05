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

        <div class="flex">
            <div v-for="(card, index) in store.cardList" :key="index">
                <Card :details="card" />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

main {
    background-color: $colorePrimario;
    // min-height: 500px;
    padding: 20px;

    section {
        width: 90%;
        margin: 0 auto;
    }

    .flex {
        display: flex;
        justify-content: center;
        margin-top: 30px;
        flex-wrap: wrap;
        gap: 8px;
        width: calc(100%/2);
        margin: 0 auto;

        background-color: white;
    }
}
</style>
