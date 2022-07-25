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
    methods: {
        outOfFive: function(vote) {
            return Math.round(vote / 2);
        },
    }
}
</script>

<style lang="scss">
ul{
    margin-bottom: 20px;
}
li {
    list-style: none;
    color: #fff;
    padding-bottom: 5px;
}
h3{
    color: #fff;
}
</style>