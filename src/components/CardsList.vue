<script>
import AppPagination from "./AppPagination.vue";
import CardsItem from "./CardsItem.vue";

import {store} from '../store.js';

export default {
    name: 'CardsList',

    components:  {
        AppPagination,
        CardsItem
    },

    data() {
        return  {
            store,
        }
    }
}
</script>

<template>
    <AppPagination></AppPagination>

    <div class="back-ground container-fluid p-5 border rounded d-flex flex-column justify-content center"> 


        <ul class="container p-5  bg-white  rounded">
            <div class="count text-uppercase container-fluid bg-dark text-white p-2 text-center">Found {{ store.cards.length }} cards</div>

            
            <CardsItem 
                v-for="currentCards in store.cards"
                :cards="currentCards"
            ></CardsItem>
           
        </ul>
    </div>
</template>

<style lang="scss">
@use '../styles/variables' as *;

ul {
    list-style-type: none;

    display: flex;
    flex-flow: row wrap;
    
    gap: $characterListGap;
    
}

.back-ground{
    background-color: $bgColour;
    

}

.count{
    font-weight: bolder;
}


</style>./CardsItem.vue/index.js