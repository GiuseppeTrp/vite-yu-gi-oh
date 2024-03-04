<script>
import {store} from '../store.js';

export default {
    name: 'AppPagination',


    data() {
        return {
            store,
        }
    }

}

</script>

<template>
    <nav>
      <div class="container-fluid text-start ">
        <h1>Yu-Gi-Oh Api</h1>
      </div>
    </nav>
    
  </template>

<style lang="scss">
@use '../styles/variables' as *;

nav {
    margin-bottom: 2em;

    padding: 24px 0;

    border-bottom: solid 1px white;

    
}




</style>