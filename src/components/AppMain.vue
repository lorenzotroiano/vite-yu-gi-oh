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
    <div class="banner">
        <span>Found {{ store.cardList.length }} cards</span>
    </div>
    <div class="listacards">



        <div class="flex">
            <div v-for="(card, index) in store.cardList" :key="index">
                <Card :details="card" />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

.banner {
    color: white;
    font-weight: bold;
    background-color: #212529;
    padding: 20px;
    margin-top: 30px;
}

.listacards {
    background-color: $colorePrimario;
    // min-height: 500px;
    padding: 20px;



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
