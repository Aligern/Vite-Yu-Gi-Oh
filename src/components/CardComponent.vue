<template>
<div class=" my-2 ">
  <img :src="img" class="card-img-top" :alt="name" >
  <div class="card-body">
    <h5 class="card-title text-center py-4">
        {{ name }}
    </h5>
    <p class="card-text text-center text-black fw-bolder">
        {{ type }}
    </p>
  </div>
</div>
</template>

<script>
    export default {
        name: "CardComponent",
        props: [
            'img',
            'name',
            'type'
        ]
    }
</script>

<style lang="scss" scoped>
@use './src/assets/styles/partials/variables' as *;
.card-body{
    min-height: 140px;
    background-color: $backgroundColor;
    color: white;
}

</style>