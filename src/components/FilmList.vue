<template>
    <div>
        <h2>
            Film List
        </h2>
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