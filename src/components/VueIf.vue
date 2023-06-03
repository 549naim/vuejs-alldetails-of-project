<template>
    <div>
        <h1> i am from vue if</h1>
        <h2 v-if="true" > v is true</h2>

        <button v-if="isActive" > button is active </button>
        <h2 v-if="number===10" >the number is :{{ number }}</h2>
        <h2 v-if="type==='Naim'" >the name is naim</h2>
        <h2 v-else-if="type==='Nai'" >the name is nai</h2>
        <h2 v-else >the name is Mr.naim</h2>
        <h2 v-if="newVar != null " >  the newcar value id is the : {{newVar}}</h2>
        
    </div>
</template>

<script setup>
import { ref, reactive } from 'vue';

const isActive = ref(true);
const number = ref(10);
const type = ref("Naim");
let newVar = ref("")



setTimeout(() => {
    const newFun=()=>{
   newVar.value ='Ek do teen char ';
}

newFun()
}, 5000);

</script>

<style lang="scss" scoped></style>