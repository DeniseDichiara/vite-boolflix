<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store.js';

export default {
  name: 'App',
  data() {
    return {
      store
    }
  },
  components: {
    AppHeader,
    AppMain
  }
}
</script>


<template>
  {{ store.searchText }}
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@import 'bootstrap/scss/bootstrap';
@import './styles/general.scss';
</style>
