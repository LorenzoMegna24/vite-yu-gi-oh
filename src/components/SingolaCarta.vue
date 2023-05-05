<script>

export default {
    name: 'SingolaCarta',
    props:['dettagliCarte']
}
</script>

<template>
    <div class="carta col-12 col-md-6 col-lg-4">
      <img :src="dettagliCarte.card_images[0].image_url" alt="">
      <h4>{{ dettagliCarte.name }}</h4>
      <span>{{ dettagliCarte.archetype }}</span>
    </div>
</template>



<style lang="scss" scoped>
.carta{   
  margin: 50px 0;
  img{
    margin-bottom: 10px;
  }
}
</style>