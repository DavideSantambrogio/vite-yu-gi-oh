<script>
import axios from 'axios';

export default {
  data() {
    return {
      selectedArchetype: '',
      cardResults: [],
    };
  },
  methods: {
    fetchCards() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
          params: {
            archetype: this.selectedArchetype,
          },
        })
        .then((response) => {
            console.log(response);
        
        })
        .catch((error) => {
          console.error('Errore nella chiamata API:', error);
        });
    },
  },
};
</script>

<template>
    <div>
        <div>
            <label for="archetypeSelect">Seleziona Archetipo:</label>
            <select v-model="selectedArchetype" @change="fetchCards">
                <option value="">Tutti</option>
                <option value="Blue-Eyes">Blue-Eyes</option>
                <option value="Dark Magician">Dark Magician</option>  
                <option value="Alien">Alien</option>
                <option value="Ancent Gear">Ancent Gear</option>              
            </select>        
        </div>
    </div>
</template>

<style scoped lang="scss">

</style>