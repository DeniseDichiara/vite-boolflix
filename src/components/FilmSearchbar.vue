<template>
    <div>
        <input type="text" name="film-search" id="film-search"
        v-model="selectedFilm" >
        <button @click="">search</button>
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
        getFilm() {
            axios.get('')
                .then(function (response) {
                    console.log(response);
                })
                .catch(function (error) {
                    console.log(error);
                })
        }
    },

    created() {
        this.getFilm();
    }
}
</script>


<style lang="scss" scoped>

</style>