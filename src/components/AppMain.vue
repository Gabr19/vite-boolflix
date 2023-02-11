<script>
  import { store } from './store'

  export default {
    name: 'AppMain',
    data(){
      return {
        store
      };
    },
    components: {},
    methods: {
      getFlag(lang){
        if(lang == 'en'){
          lang = 'uk';
        } 
        else if(lang == 'pt'){
          lang = 'po'
        }


        const flag =  `https://www.worldometers.info//img/flags/small/tn_${lang}-flag.gif` ;
      
        return flag;
      }
    },

    
  };

</script>

<template>
  <main>
    <div v-for="movie in store.movies">
      <h3>
        {{ movie.title }}
      </h3>
      <h3>
        {{ movie.original_title }}
      </h3>
      <img :src="getFlag(movie.original_language)" alt="">
      <h3>
        {{ movie.original_language }}
      </h3>
      <p>
        {{ movie.vote_average }}
      </p>
    </div>

    <div v-for="serie in store.series">
      <h3>
        {{ serie.name }}
      </h3>
      <h3>
        {{ serie.original_name }}
      </h3>
      <img :src="getFlag(serie.original_language)" alt="">
      <h3>
        {{ serie.original_language }}
      </h3>
      <p>
        {{ serie.vote_average }}
      </p>

    </div>
  </main>
  
</template>

<style lang="scss" scoped>

</style>
