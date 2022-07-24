<template>
  <div id="app">
    <HeaderApp @searchMovie="getMovies"/>
    <MainApp :movies="movies" />
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
      apiUrl : 'https://api.themoviedb.org/3/search/movie',
      movies: [],
    }
  },
  methods: {
    getMovies(needle) {
      axios.get(`${this.apiUrl}?api_key=${this.apiKey}&query=${needle}`)
      .then(result => {
        console.log(result.data.results);
        this.movies = result.data.results;
      })
      .catch(error => {
        console.log(error);
      });
    }
  }
    
}
</script>

<style>
/* @import '~fortawesome/fontawesome-free/css/all.css'; non lo legge*/
</style>