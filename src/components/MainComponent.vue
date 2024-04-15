<template>
    <main class="container bg-white my-5 ">
       <CardList />
    </main>
</template>

<script>
import CardList from './CardList.vue';
    export default {
        name: "MainComponent",
        components: {
            CardList
        }
    }
</script>

<style lang="scss" scoped>
@use './src/assets/styles/partials/variables' as *;

main{
    background-color: $backgroundColor;    
}

</style>