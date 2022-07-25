<template>
    <header>
            <div class="container">
                <div class="row">
                    <h1>Boolflix</h1>
                    <div class="search">
                        <input type="text" placeholder="Search" v-model.trim="needle">
                        <button @click="$emit('searchMovie', needle)">Cerca</button>
                    </div>
                </div>
            </div>
    </header>
</template>

<script>
export default {

    name: 'HeaderApp',

    data: function() {
        return {
            needle: '',
        }
    },
}
</script>

<style lang="scss">
header {
    background-color: #fff;
    padding: 2rem;

    .row {
        display: flex;
        justify-content: space-between;
        align-items: center;

        h1 {
            text-transform: uppercase;
            color: red;
            font-weight: 600;
            font-size: 3rem;
            width: 10rem;
            flex-grow: 0;
        }
        .search {
            flex-grow: 0;
            width: 50%;
        }
    }
}

</style>