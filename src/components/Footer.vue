<template>
  <footer class="footer">
    <p>{{ Nom }}</p>
    <p>{{ numTP }}</p>
    <p>{{ annee }}</p>
  </footer>
</template>

<!-- Script du Footer -->
  
<script>
  export default {
    data() {
      return {
        Nom: 'Victor FOURNIER BUT 2 TP A',
        numTP: 'TP 2-3 VueJS',
        annee: '2023-2024'
      };
    },
  };
</script>

<!-- CSS du Footer -->
  
<style scoped>
  .footer {
    background-color: #000000;
    text-align: center;
    color: #ffffff;
    width : 100%;
  }
</style>