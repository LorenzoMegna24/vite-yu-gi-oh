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
  <div class="d-flex justify-content-center">
    <select class="form-select w-50" aria-label="Default select example" name="cards" id="cards" v-model="store.RicercaCarte">
      <option selected="">Open this select menu</option>
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