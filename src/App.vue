<script>
   import axios from 'axios';
   import { store } from './components/store'


  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';

  export default {
    name: "App",
    data() {
      return {
        store
      };
    },
    components: {
      AppHeader,
      AppMain
    },
    methods: {
      handleSearchEvent() {
      let url = 'https://api.themoviedb.org/3/search/movie';
        axios
        .get(url, {
          params: {
            api_key: 'e99307154c6dfb0b4750f6603256716d',
            query: store.searchText,
          }
        })
        .then((response) => {
          store.movies = response.data.results;
          console.log(store.movies);
        });
      }
    }
  }

</script>

<template>
  <AppHeader @performSearch="handleSearchEvent"/>
  <AppMain/>
  
</template>

<style lang="scss" >
  @import './styles/all.scss'

</style>
