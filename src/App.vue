<template>
  <div>
    <HeaderComponent />
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
        getCards(){
          axios.get(this.store.apiUrl + this.store.endpoints.cardInfo, this.store.options).then((res) => {
          this.store.cards = res.data.data;
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