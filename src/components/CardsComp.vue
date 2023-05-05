<script>
import {store} from '../store'

import SingolaCarta from './SingolaCarta.vue'

export default {
    name: 'CardsComp',
    components: {
        SingolaCarta
    },  
    data(){
        return{
            store
        }
    }
}
</script>

<template>
    <div class="text-center row">
        <SingolaCarta
            v-for="(element,index) in store.arrayCarte"
            :key="index"
            :dettagliCarte="element"
            />
    </div>
</template>



<style lang="scss" scoped>
  
</style>