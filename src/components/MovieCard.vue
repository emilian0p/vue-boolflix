<template>
    <div>
        <h3>{{ movie.title }}</h3>
        <ul v-if="movie.title">
        <li>Titolo: {{ movie.title }}</li>
        <li>Titolo Originale: {{ movie.original_title }} </li>
        <li>Lingua Originale: {{ movie.original_language }} </li>
        <li>Voto: {{ movie.vote_average }} </li>
    </ul>
    </div>
</template>

<script>
export default {
    props: {
        movie: {
            type: Object,
            required: true,
        },
    },
}
</script>

<style>
li {
    list-style: none;
}
</style>