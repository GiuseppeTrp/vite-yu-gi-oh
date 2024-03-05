<script>
import { store } from "../store.js";

export default {
    name: 'FilterSearch',

    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="container-fluid d-flex justify-content-start p-2 gap-2 ">
        <h3>Filter</h3>
        <select name="filter" id="archetype"  class="rounded bg-dark text-white text-uppercarse ">
            <option class="text-center"  :value="archetype.archetype_name" v-for="archetype in store.archetypes" :key="archetype.id">{{ archetype.archetype_name }}</option>
        </select>
    </div>
</template>

<style>
select{
    font-weight: bold;

}

</style>
