<script>
import { store } from '../store';

export default{
  name: 'SearchComp',

  data(){
    return{
      store
    }
  },
}

</script>

<template>
  <div>
    <select name="cards" id="cards" v-model="store.RicercaCarte">Type
    <option
    v-for="(element, index) in store.arrayType"
    :key="index"
    @click.prevent="$emit('nomeEmit')"
    :value="element.archetype_name">{{ element.archetype_name }}</option>
  </select>
  </div>
</template>

<style lang="scss" scoped> 

</style>