<template>
    <div>
        <!-- using props -->
        <!-- <h1>Grand child : {{name}}</h1> -->
        <h1>Grand child : {{newName}}</h1>
        <h1>Grand child course : {{courses}}</h1>
        <!-- after destructure -->
        <h1>Grand child course destructure : {{name}} , {{duration}} ,{{fees}}</h1>

        <h1>Grand child  reactive state : {{costing}}</h1>
        <!-- <h1>from app level provide and inject : {{website}}</h1> -->


    </div>
</template>

<script setup>
import {inject} from "vue";

const newName = inject("myName");
const courses = inject("course");
// .course object destructuring
const {name , duration , fees}  = inject("course");


// inject reactive state
const costing  = inject("cost");

// app level provide and inject
// const website = inject("website");


// const props = defineProps(["name"]);

</script>

<style lang="scss" scoped>

</style>