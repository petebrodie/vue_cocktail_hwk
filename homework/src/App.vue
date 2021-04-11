<template>
  <div id="app">
    <h1>Mother's Ruin by Pete</h1>

    <label for="cocktail_select">Select A Cockatil:</label>
    <select id="cocktail_select" v-model="selectedCocktail">
      <option disabled value="">select a cocktail</option>
      <option v-for="(cocktail, index) in cocktails" :key="index" :value="cocktail">{{cocktail.strDrink}}</option>
    </select>

    <cocktail-instructions v-if="selectedCocktail" :cocktail="selectedCocktail"></cocktail-instructions>
    
  </div>
</template>

<script>
import CocktailInstructions from './components/CocktailInstructions.vue';




export default {
  name: 'App',
  data() {
    return {
      cocktails: [],
      selectedCocktail: null,
      urls: []
    }
  },
  components: {
    'cocktail-instructions': CocktailInstructions,
   

  },

  mounted() {
    this.fetchData()
  },

  methods: {
    fetchData: async function() {
      const response = await fetch("https://www.thecocktaildb.com/api/json/v1/1/search.php?s=gin")
      const data = await response.json()
      this.cocktails = data.drinks

    

    }
    
  }
}


</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  }

<style/>
