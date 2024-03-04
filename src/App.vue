<script>
// per importare axios (dopo essere stato installato) 
import axios from 'axios';

// importiamo lo store
import {store} from './store.js';

import CardsList from './components/CardsList.vue';

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
    })

  },

  components: {
    CardsList,
  },

  
}
</script>

<template>
    <CardsList></CardsList>

</template>

<style lang="scss">



</style>./components/CardsList.vue/index.js