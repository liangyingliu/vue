<script setup>
import { useMealsStore } from './store/meals';
import search from './components/search.vue';
import mealsList from './components/meals/mealsList.vue';
const meals = useMealsStore()
  console.log(meals.data);
</script>
<template>
  <search></search>
  <mealsList></mealsList>
</template>