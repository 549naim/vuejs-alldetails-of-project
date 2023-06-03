<template>
    <div>
        <!-- <button @click="$emit('countIncrease')"  >increase</button> -->

        <!-- with argument -->
        <!-- <button @click="$emit('countIncrease',5,'naim')"  >increase</button> -->

<!-- event validation -->
        <form @submit.prevent="$emit('formSubmit',name1)" >
            <p> new form</p>
            <label for="name1"> Name :</label>
            <input type="text" id="name1" v-model="name1" >
            <br>
            <br>
            <button type="submit"> Form submit</button>
        </form>


    </div>
</template>

<script setup>
import { ref } from 'vue';
const name1 = ref("");


</script>

<style lang="scss" scoped></style>