<script>
  import axios from 'axios';
  import {store} from './store'
  import HeaderComp from './components/HeaderComp.vue';
  import CardsComp from './components/CardsComp.vue';
  import SearchComp from './components/SearchComp.vue'

  export default{
    name: 'App',
    components:{
      HeaderComp,
      CardsComp,
      SearchComp
    },
    data(){
      return{
        store
      }
    },
    created(){
      this.callApi(),
      this.apiType()
    },
    methods:{
      callApi(){
        axios.get( 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=3' ).then((res)=>{
          console.log(res.data.data);

          const datiApi = res.data.data

          this.store.arrayCarte = datiApi
        })
      },
      apiType(){
        axios.get( 'https://db.ygoprodeck.com/api/v7/archetypes.php' ).then((res)=>{
          console.log(res.data);

          const datiType = res.data

          this.store.arrayType = datiType
          
        })
      }
    }
  }
</script>

<template>
 <HeaderComp/>
 <SearchComp @nomeEmit="callApi"/>
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
