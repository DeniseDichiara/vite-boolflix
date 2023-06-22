<template>
    <main>
        <h1>
            <!--?  MAIN   -->
        </h1>
        <FilmSearchbar @searched="log"/>
        <FilmList />
    </main>
</template>


<script>
import FilmSearchbar from './FilmSearchbar.vue';
import FilmList from './FilmList.vue';


export default {
    name: 'AppMain',
    data() {
        return {

        }
    },

    components: {
        FilmSearchbar,
        FilmList
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
        },
    },

    created(){

    },
}
</script>


<style lang="scss"></style>