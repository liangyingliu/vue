<script setup>
import { useMealsStore } from '../../store/meals';
const meals = useMealsStore()
const props = defineProps(["meals"])
</script>
<template>
    <div class="conter">
        <template v-if="props.meals.count>0">
            <i class="ri-subtract-line" @click="meals.subMealFromCart(props.meals)"></i>
            <span class="number">{{ props.meals.count }}</span>
        </template>
        <i class="ri-add-line" @click="meals.addMealToCart(props.meals)"></i> 
    </div>
</template>
<style scoped>
.conter i{
    border-radius: 50%;
    font-size: 18rem;
    font-weight: bold;
}
.ri-subtract-line{
    border: 1px solid;
    font-size: 18rem;
}
.ri-add-line{
    background-color: rgb(255, 194, 0);
    border: 1px solid rgb(255, 194, 0);
}
.number{
    margin: 0 10rem;
    font-size: 18rem;
    font-weight: bold;
}
</style>