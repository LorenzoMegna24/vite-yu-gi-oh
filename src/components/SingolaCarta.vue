<script>

export default {
    name: 'SingolaCarta',
    props:['dettagliCarte']
}
</script>

<template>
    <div class="carta col-12 col-md-6 col-lg-3">
      <div class="card" style="width: 18rem;">
       <img class="p-1" :src="dettagliCarte.card_images[0].image_url" alt="">
        <div class="card-body">
         <h5 class="card-title">{{ dettagliCarte.name }}</h5>
         <p class="card-text">{{ dettagliCarte.archetype }}</p>
        </div>
      </div>
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