<template>
    <header>
        <div>
            <div>
                <nav>
                    <img src="../assets/netflix-logo.png" alt="">
                    <input type="text" v-model="searchText">
                    <button @click="getMovie()">Cerca</button>
                </nav>
            </div>
        </div>
    </header>
</template> 

<script>
export default {
    name: 'HeaderApp',
    data() {
        return {
            searchText: '',
        }
    },
    methods : {
        getMovie: function() {
            this.$emit('searchMovie', this.searchText);
        }
    }
}
</script>

<style lang="scss">

</style>