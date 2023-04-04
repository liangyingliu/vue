<script setup>
import { useMealsStore } from '../../store/meals';
import mealsItem from '../meals/mealsItem.vue';
const props = defineProps(["isShow"])
const meals = useMealsStore()
</script>
<template>
    <div class="goods" v-show="props.isShow">
        <div class="top">
            <div class="detial">
                <span>餐品详情</span>
            </div>
            <div class="del">
                <i class="ri-delete-bin-5-fill"></i>
                <span> 清空购物车</span>
            </div>
        </div>
        <div class="meals">
            <mealsItem v-for="item in meals.cartMeals" :meals="item"></mealsItem>
        </div>
    </div>
</template>
<style scoped>
    .goods{
        position: fixed;
        top: 110rem;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: white;
        border-top-left-radius: 20rem;
        border-top-right-radius: 20rem;
        z-index: 9999;
    }
    .top{
        width: 100%;
        height: 50rem;
        display: flex;
        justify-content: space-between;
        line-height: 50rem;
        padding: 7rem 20rem;
    }
    .detial span{
        font-size: 15rem;
        font-weight: bold;
    }
    .del span,
    .del i{
        font-size: 13rem;
        color: rgb(143, 133, 138);
    }

</style>