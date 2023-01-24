<script>
import { store } from '../dta/store';
export default {
   name: 'AppMain', 
   data () {
    return { store }
   }
}
</script>

<template>
<div class="container d-flex justify-content-center">
    <div class="row row-cols-3 row-cols-md-4 row-cols-xl-6 ">
        <div v-for="pokemon in store.pokemons" :key="pokemon._id" class="my-3 me-3 pokemon-card">
            <img class="img-fluid" :src="pokemon.imageUrl" :alt="pokemon.name"> 
            <div class="mt-3">
                <h4 class="mb-2">{{ pokemon.name }}</h4>
                <p>{{ pokemon.type1 }} {{ pokemon.type2 }}</p>
            </div>
        </div>
    </div>
</div>
</template>

<style lang="scss">
 .pokemon-card{
    height: 300px;
    background-color: aquamarine;
    border-radius: 10px;
    padding: 15px 5px 10px 5px;
    display: flex;
    flex-direction: column;
    align-items: center;

    img{
        height: 140px;
        width: 140px;
        border-radius: 50%;
        object-fit: cover ;
    }
 }
</style>