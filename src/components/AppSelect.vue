<script >
import { store } from './../store.js';

import axios from 'axios';



export default {
    name: "AppSelect",

    data() {
        return {
            store,
        }
    },

    methods: {
        getOption() {
            axios.get(store.newApi)
                .then(res => {
                    store.optionList = res.data;

                    // console.log(store.optionList);
                })
                .catch(err => {
                    console.log(err);
                })
        }
    },
    created() {
        this.getOption();
    }
}

</script>

<template>
    <section>
        <select name="cards" id="cards" @change="$emit('search')" v-model="store.searchOption">
            <option v-for="option in store.optionList" :value="option.archetype_name">{{
                option.archetype_name }}
            </option>

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