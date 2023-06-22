<template>
    <div>
        <article v-for="film in films">
            <h2>
                {{ film.title }}
            </h2>

            <h4>
                {{ film.original_title }}
            </h4>

            <p>
                {{ film.original_language }}
                {{ film.vote_average }}
            </p>

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

    data() {
        return {
        }
    },
    components: {
        FilmCard
    }
}
</script>


<style lang="scss">
    
</style>