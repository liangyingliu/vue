<script setup>
import { useMealsStore } from './store/meals';
import search from './components/search.vue';
import mealsList from './components/meals/mealsList.vue';
import cartbar from './components/cart/cartbar.vue';
import Cartdetail from './components/cart/cartdetail.vue';
const meals = useMealsStore()
console.log(meals.cartMeals);
</script>
<template>
  <search></search>
  <mealsList></mealsList>
  <cartbar></cartbar>
  <!-- <Cartdetail></Cartdetail> -->
</template>