<template>
    <div>
        <!-- without dynamic component -->

        <!-- <h1>i ma from vue js dynamic component</h1>
        <br>
        <button @click="comp='com1'" >com 1</button>
        <button @click="comp='com2'">com 2</button>
        <button @click="comp='com3'">com 3</button>
        <br>
        <DynamicCom1 v-if="comp==='com1'" />
        <DynamicCom2 v-if="comp==='com2'"/>
        <DynamicCom3 v-if="comp==='com3'"/> -->



        <!-- with dynamic component -->

        <h1>i ma from vue js dynamic component</h1>
        <br>
        <button @click="comp='com1'" >com 1</button>
        <button @click="comp='com2'">com 2</button>
        <button @click="comp='com3'">com 3</button>
        <br>
       <component :is="tabs[comp]" />
    </div>
</template>

<script setup>
import DynamicCom1 from './DynamicCom1.vue';
import DynamicCom2 from './DynamicCom2.vue';
import DynamicCom3 from './DynamicCom3.vue';
import { ref } from 'vue';
const comp = ref("com1");

const tabs = {
   com1:DynamicCom1,
   com2:DynamicCom2,
   com3:DynamicCom3,
}

</script>

<style lang="css" scoped></style>