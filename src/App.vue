<script>
import { store } from './store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppSelect from './components/AppSelect.vue';

export default {
  components: {
    AppHeader,
    AppMain,
    AppSelect
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCards() {

      let myURL = store.apiURL;

      if (store.searchOption !== "") {
        myURL += `&archetype=${store.searchOption}`
      }
      axios.get(myURL)
        .then(res => {
          store.cardList = res.data.data;


        })
        .catch(err => {
          console.log(err);
        })
    },

  },
  created() {
    this.getCards();

  }
}
</script>

<template>
  <AppHeader />

  <main>
    <AppSelect @search="getCards" />

    <AppMain />
  </main>
</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use './styles/partials/variables.scss' as *;

main {
  background-color: $colorePrimario;
  // min-height: 500px;
  padding: 20px;
}
</style>
