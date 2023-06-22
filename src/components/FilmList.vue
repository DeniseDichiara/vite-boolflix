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
                {{ movie.original_language }}
                {{ movie.vote_average }}
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