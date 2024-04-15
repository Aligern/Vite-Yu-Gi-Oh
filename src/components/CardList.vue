<template>
    <div class="container">
        <ul>
            <li v-for="card in store.cards" :key="card.id">
                {{ card.name }}
            </li>
        </ul>
    </div>
</template>

<script>
import {store} from '../data/store.js'
    export default {
        name: "CardList",
        data(){
            return {
                store
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>