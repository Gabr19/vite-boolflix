<script>
  import { store } from './store'



  export default {
    name: 'AppMain',
    data(){
      return {
        store,
        
      };
    },
  };

</script>

<template>
  <div class="container" v-for="movie in store.movies">
    <h3>
      {{ movie.title }}
    </h3>
    <h4>
      {{movie.original_language}}
    </h4>
    <h4>
      {{ movie.vote_average }}
    </h4>
  </div>
  
  
</template>

<style lang="scss" scoped>

</style>
