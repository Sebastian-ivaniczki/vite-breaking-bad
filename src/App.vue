<script>
import axios from 'axios';
import { store } from './dta/store'
import AppHeader from './components/AppHeader.vue';
import SelectMenu from './components/SelectMenu.vue';
import AppMain from './components/AppMain.vue';
const uri = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
export default {
 components: { AppHeader, AppMain, SelectMenu },
  data() {
    return { 
      store ,
      pokemonsType: [
            "Ghost",
            "Rock",
            "Electric",
            "Poison",
            "Dark",
            "Fighting",
            "Normal",
            "Dragon",
            "Fire",
            "Fairy",
            "Steel",
            "Ground",
            "Water",
            "Flying",
            "Bug",
            "Grass",
            "Ice",
            "Psychic"
        ],
        slectedType: ''
    }
  },
  methods: {
    fetchPokemons(uri) {
      axios.get(uri)
      .then(res => {
        store.pokemons = res.data.docs
      })
    },
    fetchPokemonsType(selected) {
      this.slectedType = selected
      const uri = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=${this.selectedType}`
      this.fetchPokemons(uri)
    }
   
  }, 
  created() {
      this.fetchPokemons(uri)
    }

};

</script>

<template>
  <app-header></app-header>
  <select-menu @change-value=" fetchPokemonsType" :datas="pokemonsType"></select-menu>
  <app-main></app-main>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
