<template>
  <div class="types-container">
    <h2>Liste des Types de Pokémon</h2>
    <ul>
      <li v-for="(count, type) in typesMap" :key="type" class="type-item">
        <img :src="getTypeImage(type)" alt="Type Image" class="type-image" />
        <div class="type-info">
          <strong>{{ type }}</strong>
          <span class="type-count">{{ count }}</span>
        </div>
      </li>
    </ul>
  </div>
</template>

<!-- Script des types -->

<script>
  export default {
    data() {
      return {
        typesMap: {},
      };
    },
    
    props: {
      pokemons: [],
    },
    
    mounted() {
      this.updateTypesMap();
    },
    
    watch: {
      pokemons: 'updateTypesMap',
    },
    
    computed: {
      typesCount() {
        const countMap = {};
        this.pokemons.forEach((pokemon) => {
          const mainType = pokemon.apiTypes[0]?.name || 'Unknown';
          countMap[mainType] = (countMap[mainType] || 0) + 1;
        });
        return countMap;
      },
    },
    
    methods: {
      // Récupération des images des types des Pokémon
      getTypeImage(type) {
        const typeImages = {
          Plante:"https://static.wikia.nocookie.net/pokemongo/images/c/c5/Grass.png",
          Feu: "https://static.wikia.nocookie.net/pokemongo/images/3/30/Fire.png",
          Eau: "https://static.wikia.nocookie.net/pokemongo/images/9/9d/Water.png",
          Insecte: "https://static.wikia.nocookie.net/pokemongo/images/7/7d/Bug.png",
          Vol: "https://static.wikia.nocookie.net/pokemongo/images/7/7f/Flying.png",
          Normal: "https://static.wikia.nocookie.net/pokemongo/images/f/fb/Normal.png",
          Poison: "https://static.wikia.nocookie.net/pokemongo/images/0/05/Poison.png",
          Électrik:"https://static.wikia.nocookie.net/pokemongo/images/2/2f/Electric.png",
          Sol: "https://static.wikia.nocookie.net/pokemongo/images/8/8f/Ground.png",
          Fée: "https://static.wikia.nocookie.net/pokemongo/images/4/43/Fairy.png",
          Combat: "https://static.wikia.nocookie.net/pokemongo/images/3/30/Fighting.png",
          Psy: "https://static.wikia.nocookie.net/pokemongo/images/2/21/Psychic.png",
          Acier: "https://static.wikia.nocookie.net/pokemongo/images/c/c9/Steel.png",
          Roche: "https://static.wikia.nocookie.net/pokemongo/images/0/0b/Rock.png",
          Dragon: "https://static.wikia.nocookie.net/pokemongo/images/c/c7/Dragon.png",
          Ténèbres: "https://static.wikia.nocookie.net/pokemongo/images/0/0e/Dark.png",
          Spectre: "https://static.wikia.nocookie.net/pokemongo/images/a/ab/Ghost.png",
          Glace: "https://static.wikia.nocookie.net/pokemongo/images/7/77/Ice.png",
        };
        return typeImages[type] || "";
      },
      // Mise à jour de la liste des types des Pokémon
      updateTypesMap() {
        this.typesMap = this.typesCount;
      },
    },
  };
</script>

<!-- CSS des types -->

<style scoped>
  .types-container {
    border: 1px solid #000000;
    padding: 10px;
    border-radius: 5px;
    background-color: #f2f2f2;
    font-size: 18px;
    margin-block: 25px;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  .type-item {
    display: inline-block;
    margin: 5px;
  }

  .type-image {
    width: 60px;
    height: 60px;
  }

  .type-info {
    text-align: center;
  }

  .type-details strong {
    display: block;
    margin-bottom: 5px;
  }

  .type-count {
    display: block;
  }
</style>