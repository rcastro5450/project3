<script>
export default {
  data() {
    return {
      ingredient: '',
      direction: '',
      ingredients: JSON.parse(localStorage.getItem('ingredients')) || [],
      directions: JSON.parse(localStorage.getItem('directions')) || []
    };
  },
  methods: {
    addIngredient() {
      if (this.ingredient) {
        this.ingredients.push(this.ingredient);
        localStorage.setItem('ingredients', JSON.stringify(this.ingredients)); // Save to local storage
        this.ingredient = '';  // Clear the input field
      }
    },
    addDirection() {
      if (this.direction) {
        this.directions.push(this.direction);
        localStorage.setItem('directions', JSON.stringify(this.directions)); // Save to local storage
        this.direction = '';  // Clear the input field
      }
    }
  }
};
</script>
<template>
  <div>
    <h1>RECIPE BUILDER</h1>
    <h2>Add Ingredients</h2>
    <input v-model="ingredient" placeholder="Enter ingredient" />
    <button @click="addIngredient">Add Ingredient</button>
    <ul>
      <li v-for="(item, index) in ingredients" :key="index">{{ item }}</li>
    </ul>

    <h2>Add Directions</h2>
    <input v-model="direction" placeholder="Enter direction" />
    <button @click="addDirection">Add Direction</button>
    <ul>
      <li v-for="(item, index) in directions" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>