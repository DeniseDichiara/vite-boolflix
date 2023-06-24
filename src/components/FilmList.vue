<template>
    <div class="container">
        <div class="row p-5">
            <div class="col-12">
                <article v-for="movie in film" :movie="movie"
                    :title="movie.original_title ? movie.original_title : movie.name" :image="movie.poster_path">

                    <h2>
                        {{ movie.title ? movie.title : movie.name }}
                    </h2>

                    <h4>
                        {{ movie.original_title }}
                    </h4>


                    <div>
                        <img :src="image" alt="Poster Image">
                    </div>

                    <img v-if="languageFlagFilm(movie.original_language)" :src="getImagePath(movie.original_language)"
                        alt="Language flag" class="img-flag">
                    <span v-else>
                        {{ movie.original_language }}
                    </span>

                    <p>
                        vote: {{ movie.vote_average }}
                    </p>

                    <div>---</div>
                </article>
            </div>
        </div>

        <FilmCard />
    </div>
</template>


<script>
import FilmCard from './FilmCard.vue';

export default {
    name: 'FilmList',
    props: {
        film: Array

    },

    methods: {

        // The followong method will check if language flag is present 
        languageFlagFilm(flagName) {
            if (this.availableLanguages.includes(flagName + '.png')) {
                return true
            }
            return false;
        },

        // method for dynamic path
        getImagePath(imgSource) {
            return new URL(`../assets/img/${imgSource}.png`, import.meta.url).href;
        },



    },

    data() {
        return {
            availableLanguages: [
                'it.png', 'en.png', 'fr.png', 'ja.png', 'es.png', 'pt.png'
            ],
        }
    },
    components: {
        FilmCard
    },

    created(){
        axios.get(this.seriesApiUrl, {
                params: {
                    api_key: '8b75441ea555f4e83337de05866ffe82',
                    query : selectedFilm,
                }
            })
                .then((response) => {
                    console.log(response.data.results);
                    this.seriesList = response.data.results;
                })
                .catch(function (error) {
                    console.log(error);
                });
    }
}
</script>


<style lang="scss">
.img-flag {
    width: 40px;
    margin-bottom: .5rem;
    margin-top: 1rem;
}
</style>