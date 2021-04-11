<template>
<div id="selected_cocktail">
    <h2>{{ cocktail.strDrink }}</h2>
    <h4>Glass type: {{ cocktail.strGlass }}</h4>
    <p>Instructions: {{ cocktail.strInstructions }} </p>
    <img :src="cocktail.strDrinkThumb" alt="picture Of Cocktail">
    


</div>
  
</template>

<script>
import Ingredients from './Ingredients.vue'
export default {

    name: 'cocktail-instructions',
    props: ['cocktail'],
    components: {
        'ingredients': Ingredients
    }
    

}


</script>

<style scoped>
img {
    width: 300px;
    height: 300px;
    margin: auto;
    border-radius: 8px;

}


</style>