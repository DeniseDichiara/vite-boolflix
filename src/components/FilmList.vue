<template>
    <div>
        <article v-for="movie in film">
            <h2>
                {{ movie.title }}
            </h2>

            <h4>
                {{ movie.original_title }}
            </h4>

            <img v-if="languageFlagFilm(movie.original_language)" :src="getImagePath(movie.original_language)" alt="langua flag">
            <span v-else>
                {{ movie.original_language }}
            </span>

            <p>
                vote: {{ movie.vote_average }}
            </p>

            <div>---</div>
            

        </article>
        <FilmCard />
    </div>
</template>


<script>
import FilmCard from './FilmCard.vue';


export default {
    name: 'FilmList',
    props: {
        film : Array 

    },

    methods: {

    // The followong method will check if language flag is present 
        languageFlagFilm(flagName){
            if ( this.availableLanguages.includes(flagName+'.png')){
                return true
            }
            return false;
        },

        // method for dynamic path
        getImagePath(imgSource){
            return new URL ('../assets/img/${imgSource}.png', import.meta.url).href;
        }
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
    }
}
</script>


<style lang="scss">
    
</style>