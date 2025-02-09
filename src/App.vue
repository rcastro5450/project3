<script>
export default {
  data() {
    return {
      ingredient: '',
      direction: '',
      ingredients: [],
      directions: []
    };
  },
  methods: {
    addIngredient() {
      if (this.ingredient) {
        this.ingredients.push(this.ingredient);
        this.ingredient = '';  // Clear the input field
      }
    },
    addDirection() {
      if (this.direction) {
        this.directions.push(this.direction);
        this.direction = '';  // Clear the input field
      }
    }
  }
};
</script>
<template>
  <div>
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