<script>
export default {
    name: 'CardsItem',

    props: {
        cards: Object,
    },
}
</script>

<template>
    <li class="card cards text-white ">
        <img :src="cards.card_images[0].image_url_small" :alt="cards.name" class="border rounded">
        <div class="title">{{ cards.name }}</div>
        <div>{{ cards.archetype }}</div>
    </li>
</template>

<style lang="scss">
@use '../styles/variables' as *;

.cards {
    
    

    width: calc(100% / 3 - $characterListGap / 3 * 2);

    text-align: center;
    

    
   

}
 .cards div{
    background-color: $bgColour;
    text-transform: uppercase;
    font-weight: bold;
 }






</style>