<script>
  import { store } from './store'

  export default {
    name: 'AppHeader',
    data(){
      return{
        store
      };
    },
    
  }

</script>

<template>
  <div class="container">
    <input type="text" v-model="store.searchText">
    <button @click="$emit('performSearch')">
      Button
    </button>
  </div>
  
</template>

<style lang="scss" scoped>

</style>

