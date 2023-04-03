<script setup>
import { useMealsStore } from './store/meals';
import search from './components/search.vue';
import mealsList from './components/meals/mealsList.vue';
import cartbar from './components/cart/cartbar.vue';

const meals = useMealsStore()
</script>
<template>
  <search></search>
  <mealsList></mealsList>
  
  <cartbar></cartbar>
  
</template>