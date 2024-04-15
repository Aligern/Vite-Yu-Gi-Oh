<template>
    <div class="container">
        <div class="row">
            <div class="col-12 col-md-4 col-lg-6" v-for="card in store.cards" :key="card.id">
                <CardComponent 
                :img="card.card_images[0].image_url" :name="card.name" :type="card.archetype" />
            </div>
        </div>
    </div>
</template>

<script>
import {store} from '../data/store.js'
import CardComponent from './CardComponent.vue';
    export default {
        name: "CardList",
        components: {
            CardComponent
        },
        data(){
            return {
                store
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>