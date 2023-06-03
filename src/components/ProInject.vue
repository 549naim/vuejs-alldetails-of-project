<template>
    <div>
        <!-- using props -->
        <!-- <h1>Child : {{name}}</h1>
        <ProInjectCom name="Naim" /> -->
        <h1>Child : {{}}</h1>
        <ProInjectCom />
        <!-- provide mutation -->
        <h2>counter : {{counter}}</h2>
        <button @click="increaseFromParent" >increase from parent</button>
        <ProvideMutate/>
        
    </div>
</template>

<script setup>
import ProInjectCom from '../components/ProInjectCom.vue'
import ProvideMutate from './ProvideMutate.vue';
// const props = defineProps(["name"]);
import {provide ,ref ,readonly } from "vue"

const counter = ref(0);
provide ("counter",readonly(counter));
provide ("increaseFromParent",increaseFromParent);
function increaseFromParent() {
    counter.value ++
}


</script>

<style lang="scss" scoped>

</style>
