<script>
  import axios from 'axios';
  import {store} from './store'
  import HeaderComp from './components/HeaderComp.vue';

  export default{
    name: 'App',
    components:{
      HeaderComp,
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
          console.log(res.data);

          const datiApi = res.data

          this.store.arrayCarte = datiApi
        })
      }
    }
  }
</script>

<template>
 <HeaderComp/>
 <main class="container">
  
 </main>
</template>

<style lang="scss" scoped>
@use './style/main.scss';
</style>
