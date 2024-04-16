<template>
  <div>
    <HeaderComponent @statusSearch="setParams"/>
    <MainComponent />
  </div>
</template>

<script>
import { store } from './data/store.js';
import axios from 'axios';
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
  export default {
    name: "App",
    data(){
      return {
        store
      }
    },
    components: {
      HeaderComponent,
      MainComponent
    },
    methods: {
      setParams(){
        if (this.store.statusFilter) {
          this.store.options.params.archetype = this.store.statusFilter;
          console.log(this.store.options)
          console.log(this.store.statusFilter)
        } else {
          delete this.store.options.params.archetype
        }
        this.getCards();
      },
        getCards(){
          console.log(this.store.apiUrl + this.store.endpoints.cardInfo, this.store.options);
          axios.get(this.store.apiUrl + this.store.endpoints.cardInfo, this.store.options).then((res) => {
           
          this.store.cards = res.data.data.map((card) => {
            return {
              id: card.id,
            title: card.name,
            image: card.card_images[0].image_url,
            status: card.archetype
            }
            
          });
          //console.log(this.store.cards);
      }).catch((error) => {
        // handle error
       // console.log(error)
      }).finally(() => {
        
      });
      },
      getArchetype(){
          axios.get(this.store.apiUrl + this.store.endpoints.archetypes).then((res) => {
          this.store.archetypes = res.data.slice(0, 10);
          //console.log(this.store.archetypes);
      }).catch((error) => {
         // handle error
       // console.log(error)
        console.log(error);
      }).finally(() => {
        
      });
      }
    },
    created(){
      this.getCards();
      this.getArchetype();
    }
  }
</script>

<style lang="scss" scoped>

</style>