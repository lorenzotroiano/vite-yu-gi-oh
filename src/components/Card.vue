<script >

export default {
    name: "Card",
    props: {
        details: Object
    }
}

</script>

<template>
    <section class="cards">
        <div>
            <img :src="details.card_images[0].image_url" alt="">

            <h5>{{ details.name }}</h5>
            <span>{{ details.archetype }}</span>
        </div>

    </section>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

.cards {


    width: 120px;


    div {
        text-align: center;
        background-color: $colorePrimario;
        height: 250px;
        margin: 10px 0;

        img {
            height: 150px;
            width: 120px;
        }

        h5 {
            margin: 10px 0;
        }
    }

}
</style>