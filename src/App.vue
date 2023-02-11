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
      handleSearchEvent(){

        let url = 'https://api.themoviedb.org/3/search/';
        console.log('searchText:' , this.store.searchText);

        axios
          .get(url + 'movie', {
            params: {
              api_key: 'e99307154c6dfb0b4750f6603256716d',
              query: this.store.searchText,
            },
        })
          .then((response) =>  {
          console.log(response);
          this.store.movies = response.data.results;
        });

        axios
          .get(url + 'tv', {
            params: {
              api_key: 'e99307154c6dfb0b4750f6603256716d',
              query: this.store.searchText,
            },
        })
          .then((response) =>  {
          console.log(response);
          this.store.series = response.data.results;
        });


      }
    },
};

</script>

<template>
  <AppHeader @performSearch="handleSearchEvent"/>
  <AppMain/>
  
</template>

<style lang="scss" scoped>
  @import './styles/main.scss';

</style>
