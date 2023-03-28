<script>
import axios from 'axios';
import HeaderApp from './components/HeaderApp.vue';
import MainApp from './components/MainApp.vue';

import { store } from './store';

export default {
  name: 'App',
  components: {
    HeaderApp,
    MainApp
  },
    data() {
        return {
            store,
        }
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')  
        .then((response) => {
            this.store.cards = response.data.data;
            this.store.cardsFound = response.data.data.length;
        })
    },
    methods: {
      searchCards() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
          params: {
            archetype: store.selectValue
          }
        })  
        .then((response) => {
            this.store.cards = response.data.data;
            this.store.cardsFound = response.data.data.length;
        })
      }
    }
}
</script>

<template>
  <HeaderApp />
  <MainApp @search="searchCards"/>
</template>

<style lang="scss"></style>