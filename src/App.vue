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
      axios.get(store.apiURL)
        .then(res => {
          store.cardList = res.data.data;


        })
        .catch(err => {
          console.log(err);
        })
    }
  },
  created() {
    this.getCards();
  }
}
</script>

<template>
  <AppHeader />

  <main>
    <AppSelect />

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
