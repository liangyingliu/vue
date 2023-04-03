<script setup>
import {ref} from "vue"
import bag from "../../assets/bag.png"
import { useMealsStore } from "../../store/meals";
import Mask from "../UI/mask.vue";
const meals = useMealsStore()
const showditial=ref(false)
</script>
<template>
    <Mask :is-show="showditial" @hide="showditial=false"></Mask>
    <div class="cartbar">
        <div class="all">
            <div class="bag">
                <img :src="bag" >
                <span class="bag_count" v-if="meals.totalCount!=0">{{meals.totalCount}}</span>
            </div>
            <div class="main">
                <p class="no_goods" v-if="meals.totalCount==0">未选购任何商品</p>
                <div class="h" v-if="meals.totalCount!=0">
                    <p class="rmb">￥</p>
                    <p @click="showditial=~showditial" class="have_goods">{{ meals.amount }}</p>
                </div>
               
            </div>
            <button class="n_goods" v-if="meals.totalCount==0">去结算</button>
            <button class="h_goods" v-if="meals.totalCount!=0">去结算</button>
        </div>
    </div>
</template>
<style scoped>
.cartbar{
    width: 350rem;
    height: 50rem;
    background-color: rgb(58, 58, 58);
    position: fixed;
    bottom: 20rem;
    left: 20rem;
    border-radius: 30rem;
    z-index: 9999;
}
img{
    width: 50rem;
    position: absolute;
    left: 0;
    bottom: -5rem
}
.n_goods{
    width: 100rem;
    height: 100%;
    background-color: rgb(108, 107, 107);
    position: absolute;
    right: 0;
    bottom: 0;
    border-radius: 30rem;
    border: 1px solid rgb(108, 107, 107);
    font-size: 20rem;
    color: rgb(160, 170, 170);
}
.h_goods{
    width: 100rem;
    height: 100%;
    background-color: rgb(255, 194, 0);
    position: absolute;
    right: 0;
    bottom: 0;
    border-radius: 30rem;
    border: 1px solid rgb(255, 194, 0);
    font-size: 20rem;
    color: black;
}
.bag_count{
    width: 20rem;
    height: 20rem;
    background-color: red;
    position: absolute;
    top: -10rem;
    left: 40rem;
    border-radius: 50%;
    color: white;
    font-weight: bold;
    text-align: center;
    line-height: 20rem;
    font-size: 12rem;
}
.main p{
    height: 100%;
    position: absolute;
    left: 60rem;
    font-weight: bold;
}
.no_goods{
    color: rgb(160, 170, 170);
    font-size: 18rem;
    line-height: 50rem;
}
.have_goods{
    margin-left: 15rem;
    color: rgb(255, 255, 255);
    font-size: 22rem;
    line-height: 50rem;
}
.rmb{
    position: absolute;
    bottom: -20rem;
    font-size: 12rem;
    color: rgb(255, 255, 255);
}

</style>