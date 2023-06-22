<template>
    <main>
        <h1>
            <!--?  MAIN   -->
        </h1>
        <FilmSearchbar @searched="getFilm" />
        <FilmList :film="filmList"/>
    </main>
</template>


<script>
import FilmSearchbar from './FilmSearchbar.vue';
import FilmList from './FilmList.vue';
import axios from 'axios';

export default {
    name: 'AppMain',
    data() {
        return {
            filmApiUrl : ' https://api.themoviedb.org/3/search/movie',
            filmList: [],
        }
    },

    components: {
        FilmSearchbar,
        FilmList
    },

    methods: {
        getFilm(selectedFilm) {
            axios.get(this.filmApiUrl, {
                params: {
                    api_key: '8b75441ea555f4e83337de05866ffe82',
                    query:selectedFilm,
                }
            })
                .then((response) => {
                    console.log(response.data.results);
                    this.filmList = response.data.results;
                })
                .catch(function (error) {
                    console.log(error);
                });
        },
    },

    created() {
        this.getFilm();
    },
}
</script>


<style lang="scss"></style>