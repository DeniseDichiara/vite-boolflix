<template>
    <div>
        <input type="text" name="film-search" id="film-search"
        v-model="selectedFilm" >
        <button @click="$emit('searched' , selectedFilm)">search</button>
    </div>
</template>


<script>

export default {
    name: 'FilmSearchbar',

    data() {
        return {
            selectedFilm: ''
        }
    },

    methods: {
    },

    created() {
        
    }
}
</script>


<style lang="scss" scoped>

</style>