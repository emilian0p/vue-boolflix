<template>
    <header>
            <div class="d-flex justify-content-between">
                <img src="../assets/netflix-logo.png" alt="">
            
                <input type="text" placeholder="Search" v-model.trim="needle">
                <button @click="$emit('searchMovie', needle)">Cerca</button>
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

<style>
</style>