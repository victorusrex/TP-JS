<template>
  <div id="app">
    
    <!-- Affichage du titre -->
    <h1>TP Pokemon</h1>

    <!-- Affichage des Pokémon -->
    <main>
      <router-view></router-view>
    </main>   
    
    <!-- Affichage du footer -->
    <Footer/>
  </div>
</template>


<script>
  import Pokedex from './components/Pokedex.vue';
  import Footer from './components/Footer.vue';

  export default {
    components: {
      Pokedex,
      Footer
    },
  };
</script>