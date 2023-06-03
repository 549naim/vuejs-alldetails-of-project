<script setup>
import NewFile2 from './NewFile2.vue';


const msg= ' new msg from child components'
</script>

<template>
    <div>
         {{ msg }}

         <NewFile2/>
    </div>
</template>



<style  scoped>

</style>