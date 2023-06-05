<script >

export default {
    name: "AppHeader"
}

</script>

<template>
    <header>
        <img src="https://ygoprodeck.com/cdn-cgi/image/width=150/https://images.ygoprodeck.com/assets/images/ygoprodeck_logo.png"
            alt="">
        <h1>Yu Gi Ho API</h1>
    </header>
</template>

<style lang="scss" scoped>
header {
    height: 100px;
    padding: 20px;
    display: flex;
    align-items: center;

    img {
        margin-right: 20px;
        height: 30px;
    }

    h1 {
        font-size: 30px;
    }
}
</style>
