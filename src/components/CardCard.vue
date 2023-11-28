<script>
export default {
    props: {
        card: Object
    }

}

</script>

<template>
    <div class="card h-100" >
  <img :src="card.card_images[0].image_url_small" class="card-img-top" alt="...">
  <div class="card-body text-center">
    <h5 class="card-title">{{ card.name }}</h5>
    <p class="card-text">{{ card.archetype ? card.archetype : "Nessun archetipo"}}</p>
    
  </div>
</div>
    
</template>

<style lang="scss" scoped>


</style>