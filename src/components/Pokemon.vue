<template>
  <div class="pokemon-card" :class="getBackgroundColor()">
    <img :src="pokemon.image" alt="Pokemon Image" class="pokemon-image" />
    <div class="pokemon-details">
      <h6>Génération {{ pokemon.apiGeneration }}</h6>
      <h3>{{ pokemon.name }}</h3>
      <div v-for="type in pokemon.apiTypes" :key="type.name" class="type-info" >
        <img :src="type.image" alt="Type Image" class="type-image" />
        <span>{{ type.name }}</span>
      </div>
    </div>
  </div>
</template>

// Script du Pokemon

<script>
  export default {
    props: {
      pokemon: Object,
    },
    
    methods: {
      getBackgroundColor() {
        if (this.pokemon.apiTypes.length > 0) {
          return this.pokemon.apiTypes[0].name.toLowerCase();
        }
        return ''; 
      },
    },
  };
</script>

// CSS du Pokemon

<style scoped>
  .pokemon-card {
    display: flex;
    border: solid 1px black;
    color: black;
    font-size: 15px;
    text-decoration: underline;  
    margin-bottom: 15px;
  }

  .pokemon-details {
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .type-info {
    display: flex;
    align-items: center;
  }

  /* Couelur des types des Pokémon */
  .plante {
    background-color: green;
  }
  .poison {
    background-color: purple; 
  }
  .eau {
    background-color: blue;
  }
  .feu {
    background-color: red;
  }
  .vol {
    background-color: rgb(0, 217, 255);
  }
  .insecte {
    background-color: rgb(10, 96, 21);
  }
  .normal {
    background-color: grey;
  }

  .électrik {
    background-color: yellow;
  }

  .sol{
    background-color: brown;
  }

  .fée {
    background-color: pink;
  }
  .combat {
    background-color: rgb(255, 118, 97);
  }

  .acier {
    background-color: rgb(121, 188, 210);
  } 

  .glace {
    background-color: rgb(110, 214, 204);
  }
  .roche{
    background-color: rgb(196, 177, 99);
  }

  .dragon {
    background-color: rgb(30, 119, 185);
  }
  .psy {
    background-color: rgb(236, 65, 102);
  }

  .ténèbres {
    background-color: rgb(121, 34, 44);
  }

  .spectre {
    background-color: rgb(113, 103, 134);
  }
  .pokemon-image {
    width: 100%;
  }
</style>