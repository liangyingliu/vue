<script setup>
import {ref} from "vue"
const count=ref(0)
</script>
<template>
    <div class="conter">
        <template v-if="count>0">
            <i class="ri-subtract-line" @click="count--"></i>
            <span class="number">{{ count }}</span>
        </template>
        <i class="ri-add-line" @click="count++"></i> 
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
    background-color: yellow;
    border: 1px solid yellow;
}
.number{
    margin: 0 10rem;
    font-size: 18rem;
    font-weight: bold;
}
</style>