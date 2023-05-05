<script>
  import axios from 'axios';
  import {store} from './store'
  import HeaderComp from './components/HeaderComp.vue';
  import CardsComp from './components/CardsComp.vue';

  export default{
    name: 'App',
    components:{
      HeaderComp,
      CardsComp,
    },
    data(){
      return{
        store
      }
    },
    created(){
      this.callApi()
    },
    methods:{
      callApi(){
        axios.get( 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=3' ).then((res)=>{
          console.log(res.data.data);

          const datiApi = res.data.data

          this.store.arrayCarte = datiApi
        })
      }
    }
  }
</script>

<template>
 <HeaderComp/>
 <main class="container">
  <CardsComp/>
 </main>
</template>

<style lang="scss">
@use './style/main.scss';
body{
  background-color: rgb(255, 166, 0);
}

</style>
