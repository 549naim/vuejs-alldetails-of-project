<template>
    <div>
        <asyncUser v-if="showUserCom" />
        <button @click="showUserCom =! showUserCom " >Show user</button>

    </div>
</template>

<script setup>
import { ref ,defineAsyncComponent } from 'vue';

const showUserCom = ref(false);

const asyncUser = defineAsyncComponent(()=>
import ("../components/AsyncChild.vue")
);

</script>

<style lang="scss" scoped>

</style>