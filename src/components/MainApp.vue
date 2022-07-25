<template>
    <main>
        <MovieCard v-for="movie in movies" :key="movie.id" :movie="movie"/>
    </main>
</template>

<script>
import MovieCard from './MovieCard.vue';

export default {
    components:{
        MovieCard
    },
    props: {
        movies: {
            type: Array,
        },
        series: {
            type: Array,
        },
    },
}
</script>

<style>
main{
    display: flex;
    
}
</style>