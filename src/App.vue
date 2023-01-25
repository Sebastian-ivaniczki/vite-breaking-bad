<script>
import axios from 'axios';
import { store } from './dta/store'
import AppHeader from './components/AppHeader.vue';
import SelectMenu from './components/SelectMenu.vue';
import AppMain from './components/AppMain.vue';
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
        ]
    }
  },
  methods: {
    fetchPokemons() {
      axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=1')
      .then(res => {
        store.pokemons = res.data.docs
      })
    }
   
  }, 
  created() {
      this.fetchPokemons()
    }

};

</script>

<template>
  <app-header></app-header>
  <select-menu :datas="pokemonsType"></select-menu>
  <app-main></app-main>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
