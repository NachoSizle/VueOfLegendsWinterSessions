<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <CharacterCard v-for="character in filteredList"
      :key="character.uid"
      :character="character"
      v-show="character.difficulty >= 6"
      ></CharacterCard>

    <button @click="setTypeToShow('MID')">Show MID</button>
    <button @click="setTypeToShow('TOP')">Show TOP</button>
    <button @click="setTypeToShow('ALL')">Show ALL Characters</button>
  </div>
</template>

<script>
import CharacterCard from './components/CharacterCard.vue';
import CharactersList from './assets/favCharacters.json';

export default {
  name: 'App',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      charactersList: [],
      typeToShow: 'ALL',
    };
  },
  computed: {
    filteredList() {
      const { charactersList, typeToShow } = this;
      if (typeToShow === 'ALL') {
        return charactersList;
      }
      return charactersList.filter((character) => character.recommended_lanes.includes(typeToShow));
    },
  },
  watch: {
    typeToShow() {
      console.log(this.typeToShow);
    },
  },
  components: {
    CharacterCard,
  },
  methods: {
    setTypeToShow(type) {
      this.typeToShow = type;
    },
  },
  beforeMount() {
    this.charactersList = CharactersList;
    console.log(this.charactersList);
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
