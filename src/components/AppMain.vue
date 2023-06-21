<template>
    <main>
        <h1>
            Main
        </h1>
        <FilmList />
    </main>
</template>


<script>
import FilmList from './FilmList.vue';

export default {
    name: 'AppMain',
    data() {
        return {

        }
    },
    components: {
        FilmList
    }
}
</script>


<style lang="scss"></style>