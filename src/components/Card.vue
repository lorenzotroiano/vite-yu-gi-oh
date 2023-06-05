<script >

export default {
    name: "Card",
    props: Object
}

</script>

<template>
    <section class="flex-cards">
        <div>
            <img src="https://images.ygoprodeck.com/images/cards_cropped/89185742.jpg" alt="">

            <h5>Lorenzo</h5>
            <span>Umano</span>
        </div>

    </section>
</template>

<style lang="scss" scoped>
.flex-cards {
    display: flex;
    justify-content: flex-start;
    margin-top: 30px;
    flex-wrap: wrap;
    gap: 10px;

    div {
        text-align: center;

        img {
            height: 150px;
            width: 120px;
        }
    }

}
</style>