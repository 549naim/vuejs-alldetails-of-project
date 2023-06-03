<template>
    <div>
        <h1>i am from image view</h1>
        <img src="../assets/img/vue.png" alt=" image" width="150" height="100">
        <img src="../assets/img/vue2.jpg" alt=" image" width="150" height="100">
        <img src="../assets/img/web 1.png" alt=" image" width="150" height="100">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/640px-Vue.js_Logo_2.svg.png"
            alt=" image" width="150" height="100">
        <br>
        <img :src="image" alt=" image" width="150" height="100">
    </div>
</template>

<script setup>
import { ref } from 'vue';

const image = ref(
    "https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/640px-Vue.js_Logo_2.svg.png"
)

</script>

<style lang="scss" scoped></style>