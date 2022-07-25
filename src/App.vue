<template>
  <div id="app">
    <HeaderApp @searchMovie="getSomethingToSee"/>
    <MainApp
    :movies="movies" 
    :series='series'/>
  </div>
</template>

<script>

import axios from 'axios';
import HeaderApp from './components/HeaderApp.vue';
import MainApp from './components/MainApp.vue';

export default {
  components : {
    HeaderApp,
    MainApp
  },
  data: function() {
    return {
      apiKey : '105531e0b71d5b1984d1ce28e4125c24',
      apiMovieUrl : 'https://api.themoviedb.org/3/search/movie',
      apiSeriesUrl : 'https://api.themoviedb.org/3/search/tv',
      movies: [],
      series: [],
      searchText: '',
    }
  },
  methods: {
    getSomethingToSee(needle) {

      axios.get(`${this.apiMovieUrl}?api_key=${this.apiKey}&query=${needle}`)
      .then(result => {
        this.movies = result.data.results;
      })
      .catch(error => {
        console.log(error);
      });

      axios.get(`${this.apiSeriesUrl}?api_key=${this.apiKey}&query=${needle}`)
      .then(result => {
        this.series = result.data.results;
      })
      .catch(error => {
        console.log(error);
      });
    },

    created() {
      this.getSomethingToSee('star wars');
    },
  }
    
}
</script>

<style lang="scss">
/* @import "~@fortawesome/"; */
@import "./style/common.scss";
</style>