<template>
    <div>
        <article v-for="movie in film">
            <h2>
                {{ movie.title }}
            </h2>

            <h4>
                {{ movie.original_title }}
            </h4>

            <p>
                lang: {{ movie.original_language }} 
                {{ currentLanguage }}
                
                <img src="/img/en.png">
                <img src="/img/fr.png">
                <img src="/img/ja.png">
                <img src="/img/pt.png">

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

    },

    data() {
        return {
            currentLanguage: 'null',
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