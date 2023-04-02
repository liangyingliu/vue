<script setup>
import conter from '../UI/conter.vue'
const props = defineProps(["meals"])
console.log(props);
</script>
<template>
    <div class="item">
       <div class="photo">
           <img :src="props.meals.img">
       </div> 
       <div class="info">
            <span class="name">{{ props.meals.title }}</span>
            <span class="ditail">{{ props.meals.desc }}</span>
            <div class="bottom">
                <div class="price">
                    <span class="rmb">￥</span>
                    <span class="math">{{ props.meals.price }}</span>
                </div>
                <conter></conter>   
            </div>
       </div>
    </div>
</template>
<style scoped>
.item{
    width: 100%;
    height: 150rem;
    background-color: rgb(255, 255, 255);
    margin: 0 auto;
    border-top: 1px solid rgb(242, 242, 242);
    position: relative;
    display: flex;
    flex-direction: row;
}
.photo{
    width: 125rem;
    height: 125rem;
    margin:0 25rem;
    margin-top: 20rem;
}
img{
    width: 110rem;
}
.info{
    display: flex;
    flex-direction: column;
    margin: 20rem 25rem 20rem 0;   
    position: relative;
}
.name{
    font-size: 16rem;
    margin-bottom: 5rem; 
}
.ditail{
    font-size: 10rem;
    color: rgb(204, 191, 185);
}
.price{
    font-weight: bolder;
}
.rmb{
    font-size: 12rem;
}
.math{
    font-size: 20rem;
}
.bottom{
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    position: absolute;
    bottom: 0;
}
</style>