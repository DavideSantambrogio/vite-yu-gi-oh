<script>
import axios from 'axios';

export default {
  data() {
    return {
      selectedArchetype: '',
    };
  },
  methods: {
    selectCard() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
          params: {
            archetype: this.selectedArchetype,
          },
        })
        .then((response) => {
          this.$emit('updateCards', response.data.data);
        })
        
    },
  },
};
</script>

<template>
  <div>
    <div>
      <label for="archetypeSelect">Seleziona Archetipo:</label>
      <select v-model="selectedArchetype" @change="selectCard">
        <option value="">Tutti</option>
        <option value="Blue-Eyes">Blue-Eyes</option>
        <option value="Dark Magician">Dark Magician</option>
        <option value="Alien">Alien</option>
        <option value="Ancient Gear">Ancient Gear</option>
        <option value="Red-Eyes">Red-Eyes</option>
        <option value="Machina">Mek</option>
        <option value="Toon">Toon</option>
        <option value="Synchron">Synchron</option>
        <option value="Exodia">Exodia</option>
        <option value="Elemental Hero">Elemental Hero</option>
        <option value="Blackwing">Blackwing</option>
        <option value="Lightsworn">Lightsworn</option>
        <option value="Subterror">Subterror</option>
        <option value="Harpie">Harpie</option>
        <option value="Ojama">Ojama</option>
        <option value="Cyberdark">Cyberdark</option>
        
        
      </select>
    </div>
  </div>
</template>

<style scoped lang="scss">
</style>