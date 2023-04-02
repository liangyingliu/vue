<script setup>
import { useMealsStore } from '../../store/meals';
import mealsItem from './mealsItem.vue';
const meals = useMealsStore()
</script>
<template>
    <div class="meals">
        <mealsItem v-for="item in meals.filterMeals" :meals="item"></mealsItem>
    </div>
</template>
<style scoped>
.meals{
    height: calc(100vh - 65rem);
    overflow: auto;
    padding-bottom: 70rem;
}
</style>