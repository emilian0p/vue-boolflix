<template>
    <header>
            <div>
                <img src="../assets/netflix-logo.png" alt="">
            </div>
            <input type="text" placeholder="Search" v-model="needle">
            <button @click="$emit('searchMovie', needle)">Cerca</button>

    </header>
</template>

<script>
export default {
    data: function() {
        return {
            needle: '',
        }
    },
}
</script>

<style>

</style>