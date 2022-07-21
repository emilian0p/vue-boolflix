<template>
    <div id="app">
      <HeaderApp @searchMovie="getMovie"/>
      <MainApp />
    </div>
</template>

<script>
import HeaderApp from './components/HeaderApp.vue';
import MainApp from './components/MainApp.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    HeaderApp,
    MainApp
  },
  data() {
    return {
      moviesArray: [],
      apiCallback: 'https://api.themoviedb.org/3/search/movie?api_key=762e8d8371364239e7194e5712ca4d7b&query=',
    }
  },
  methods: {
    getMovie: function(search) {
      axios.get(this.apiCallback + search)
      .then(response => {
        console.log(response.data.results);
        this.moviesArray = response.data.results;
      })
      .catch(error => {
        console.warn(error);
      });
    }
  },
  created(){
      this.getMovie();
  }

}
</script>

<style>

</style>