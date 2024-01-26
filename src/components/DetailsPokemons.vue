<template>
  <div>
    <h1>{{ pokemon.name }}</h1>

    <!-- Afficher l'image du Pokémon avec les logos et noms des types -->

    <div>
      <img :src="pokemon.image" alt="Pokemon Image" />
      <div v-if="pokemon.types && pokemon.types.length" class="types-container">
        <p>Types:</p>
        <div v-for="type in pokemon.types" :key="type.name" class="type-item">
          <img :src="getTypeLogoUrl(type.name)" alt="Type Logo" />
          <span>{{ type.name }}</span>
        </div>
      </div>
    </div>

    <!-- Afficher les statistiques du Pokémon -->

    <div v-if="pokemon.stats" class="stats-container">
      <h2>Statistiques du Pokémon ayant l'identifiant {{ pokemon.id }} :</h2>
      <ul>
        <li><strong>Points de vie :</strong> {{ pokemon.stats.HP }}</li>
        <li><strong>Points d'attaque :</strong> {{ pokemon.stats.attack }}</li>
        <li><strong>Points de défense :</strong> {{ pokemon.stats.defense }}</li>
        <li><strong>Attaque spéciale :</strong> {{ pokemon.stats.special_attack }}</li>
        <li><strong>Défense spéciale :</strong> {{ pokemon.stats.special_defense }}</li>
        <li><strong>Rapidité :</strong> {{ pokemon.stats.speed }}</li>
      </ul>
    </div>
  </div>
</template>

<!--  CSS des pages des détails des Pokemons -->

<style>
.types-container {
  display: flex;
  align-items: center;
}

.type-item {
  margin-right: 10px;
}

.stats-container {
  background-color: #938d8d;
  padding: 15px;
  margin-top: 15px;
  border-radius: 8px;
}

.stats-container ul {
  list-style-type: none;
  padding: 0;
}

.stats-container li {
  margin-bottom: 10px;
}

.stats-container li strong {
  font-weight: bold;
}
</style>

<!-- Script des pages des détails des Pokemons -->

<script>
import axios from 'axios';

export default {
  data() {
    return {
      pokemon: {},
    };
  },

  created() {
    // Accéder à l'identifiant depuis les paramètres de la route
    const pokemonId = this.$route.params.id;

    // Récupération des détails du Pokémon
    this.fetchPokemonDetails(pokemonId);
  },
  
  methods: {
    fetchPokemonDetails(id) {
      // Appel de l'API
      axios.get(`https://pokebuildapi.fr/api/v1/pokemon/${id}`)
        .then(response => {
          this.pokemon = response.data;
        })
        .catch(error => {
          console.error('Error fetching Pokemon details:', error);
        });
    },
  },
};
</script>