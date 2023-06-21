<template>
    <div>
        <lable for="film-search"></lable>
        <select name="film-search" id="film-search" v-model="selectedFilm">
            <option v-for="" value="">

            </option>

        </select>
    </div>
</template>


<script>
import axios from 'axios';

export default {
    name: 'FilmSearchbar',
    data() {
        return {
            selectedFilm: ''
        }
    },

    methods: {
        getFilm() {
            axios.get('')
                .then(function (response) {
                    console.log(response);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
        }
    },

    created() {
        this.getFilm();
    }
}
</script>


<style lang="scss" scoped></style>