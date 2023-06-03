<template>
    <div>
        <h1>i am from async child</h1>
        <h3 v-for="user in users" >{{user}}</h3>

    </div>
</template>

<script setup>
import {ref} from "vue";

const users = ref(["naim" , "rakibul" , "islam"]);

</script>

<style lang="scss" scoped>

</style>