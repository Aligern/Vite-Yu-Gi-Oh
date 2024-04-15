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
          axios.get(this.store.apiUrl).then((res) => {
          this.store.cards = res.data.data
          console.log(this.store.cards);
      })
      }
    },
    created(){
      this.getCards();
    }
  }
</script>

<style lang="scss" scoped>

</style>