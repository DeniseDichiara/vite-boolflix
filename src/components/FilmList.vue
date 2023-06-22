<template>
    <div>
        <h2>
            <!--todo  FILM LIST   -->
        </h2>
        <FilmCard />
    </div>
</template>


<script>
import FilmCard from './FilmCard.vue';


export default {
    name: 'FilmList',
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