<template>
    <h3>Choisissez le nombre de pokémons que vous souhaitez :</h3>
    <div>
      <input type="number" v-model="nbPok" @input="fetchPokemons" min="1"/> <!-- Condition du minimum de pokémon choisi est de 1 -->
      <ListesTypesPokemon v-if="pokemons.length > 0" :pokemons="pokemons" />
      <div v-if="pokemons.length > 0">
          <a v-for="pokemon in pokemons" :key="pokemon.name" :pokemon="pokemon" :href = "`/pokemon/${pokemon.id}`">
              <Pokemon :pokemon="pokemon" />
          </a>
      </div>
    </div>
</template>

<!-- Script du Pokedex -->
  
<script>
  import axios from 'axios';
  import Pokemon from './Pokemon.vue';
  import ListesTypesPokemon from './ListesTypesPokemon.vue';
  
  export default {
    components: {
      Pokemon, ListesTypesPokemon
    },
   
    data() {
      return {
        pokemons: [],
        nbPok: 10, // Valeur choisie par défaut
      };
    },
    
    mounted() {
      this.fetchPokemons();
    },
    
    methods: {
      fetchPokemons() {
        // Appel de l'API
        axios.get(`https://pokebuildapi.fr/api/v1/pokemon/limit/${this.nbPok}`)
          .then(response => {
            this.pokemons = response.data;
          })
          .catch(error => {
            console.error('Error fetching Pokemon data:', error);
          });
      },
    },
  };
</script>  

<!-- CSS pour l'input -->

<style scoped>
  input {
    width: 100px;
    height: 25px;
    border-radius: 5px;
    border: 1px solid black;
    margin-bottom: 25px;
  }
</style>