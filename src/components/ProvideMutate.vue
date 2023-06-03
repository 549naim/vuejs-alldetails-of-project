<template>
    <div>
        <h1>i am from provide mutate</h1>
        <h2>counter : {{counter}}</h2>
        <button @click="increaseFromParent" >increase from child</button>
    </div>
</template>

<script setup>
import {inject } from "vue"
const counter = inject("counter")
const increaseFromParent = inject("increaseFromParent")

// function increaseFromChild() {
//     counter.value ++
// }

</script>

<style lang="scss" scoped>

</style>