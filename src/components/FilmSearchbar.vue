<template>
    <div>
        <input type="text" name="film-search" id="film-search"
        v-model="selectedFilm" >
        <button @click="$emit('searched' , selectedFilm)">search</button>
    </div>
</template>


<script>
import axios from 'axios';

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
        this.getFilm();
    }
}
</script>


<style lang="scss" scoped>

</style>