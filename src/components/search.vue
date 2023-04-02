<script setup>
import { useMealsStore } from '@/store/meals';
const meals = useMealsStore()
</script>

<template>
    <div class="search">
        <i class="ri-search-line"></i>
        <input type="text" placeholder="请输入关键字" v-model="meals.keyword">
        <template v-if="meals.filterMeals.length==0">
            <h2>未找到该商品</h2>
        </template>
    </div>
</template>
<style scoped>
.search{
    width: 350rem;
    height: 35rem;
    background-color: rgb(242, 242, 242);
    margin: 0 auto;
    margin-top: 15rem;
    margin-bottom: 15rem;
    border-radius: 15rem;
    position: relative;
    line-height: 35rem;
}

i{
    font-size: 20rem;
    color: rgb(176, 175, 175);
    align-items: center;
    position: absolute;
    left: 8rem;
}
input{
    width: 290rem;
    height: 35rem;
    border: none;
    background-color:rgb(242, 242, 242);
    position: absolute;
    left: 35rem;  
    font-size: 14rem;
}
input:focus{
    outline: none;
}
h2{
    position: absolute;
    top: 150rem;
    width: 350rem;
    background-color: rgb(56, 56, 56);
    color: white;
    font-size: 20rem;
    text-align: center;
    border-radius: 5rem;
    box-shadow: 0 0 5px black;
}
</style>