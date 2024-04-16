<template>
    <div class="bg-white p-2">
        <h1>Yu-Gi-Oh!</h1>
        <select class="form-select" id="searchBar" @change="$emit('statusSearch')" v-model="store.statusFilter">
            <option value="">
                All
            </option>
            <option :value="archetypes.archetype_name" v-for="archetypes in store.archetypes">
            {{ 
                archetypes.archetype_name
             }}
            </option>
        </select>
    </div>
</template>

<script>
import { store } from '../data/store.js';
    export default {
        name: "HeaderComponent",
        data(){
            return {
                store
            }
        }
    }
</script>

<style lang="scss" scoped>
#searchBar  {
    width: 250px;
}
</style>