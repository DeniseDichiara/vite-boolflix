<template>
    <main>
        <h1>
            <!--?  MAIN   -->
        </h1>
        <FilmSearchbar />
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
    }
}
</script>


<style lang="scss"></style>