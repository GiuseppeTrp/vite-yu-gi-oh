<script>
// per importare axios (dopo essere stato installato) 
import axios from 'axios';

// importiamo lo store
import {store} from './store.js';

import CardsList from './components/CardsList.vue';
import FilterSearch from './components/FilterSearch.vue'
import AppPagination from "./components/AppPagination.vue";

export default {
  data() {
    return {
      cards: [],

      // dichiariamo lo store, utilizzabile nel nostro componente
      store,
    }
  },

  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
      console.log(res)
      this.store.cards = res.data.data;
    }).catch(err => {
      console.log(err)
    });

    axios
      .get(`https://db.ygoprodeck.com/api/v7/archetypes.php`)    
      .then(res => {
        this.store.archetypes = res.data;
        console.log(this.store.archetypes)
      }).catch(err => {
        console.log(err)
      });

  },
    
  methods: {
    searchCard() {
      console.log("search ");

      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(res => {
          console.log(res.data)
          this.store.archetypes = res.data;
        });
    },
   
  },

  components: {
    CardsList,
    FilterSearch,
    AppPagination,
  },
}
</script>

<template>
    <AppPagination></AppPagination>
    <FilterSearch></FilterSearch>
    <CardsList> </CardsList>
</template>

<style lang="scss">
</style>
