<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';
import {store} from "./store"


export default {    
  components: {
    AppHeader,
    CardsList,    
  },
  data() {
    return {
      store
      
    }
  },
  created() {
    this.getCards()
  },
  methods: {
    getCards() {
      axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((resp) => {
        this.store.cardsList = resp.data.data
      })      
    }
  },

}

</script>

<template>
  <AppHeader/>
  <CardsList/>
  

</template>

<style lang="scss">
@use './style/general.scss';


</style>
