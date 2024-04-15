<template>
<div class="card my-2 ">
  <img :src="img" class="card-img-top" :alt="name" >
  <div class="card-body">
    <h5 class="card-title">
        {{ name }}
    </h5>
    <p class="card-text">
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

</style>