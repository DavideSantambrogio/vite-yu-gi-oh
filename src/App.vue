<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import {store} from './store.js';




export default {
    data() {
        return {
          store,
        };
    },
    created() {
      this.store.loading = true;
      axios
        .get(this.store.apiUrl)
        .then((resp) => {
          this.store.cardsList = resp.data;
          this.store.loading = false;
        });
    },
    components: { 
        AppHeader, 
         
    }
}

</script>

<template>
  <AppHeader/>
  

</template>

<style lang="scss">
@use './style/general.scss';


</style>
