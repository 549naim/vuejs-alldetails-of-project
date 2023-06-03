<!-- methods with reactive or without reactive  -->

<template>
    <div>
the full Name is : {{ newFun(102) }}
<h3>i am from computed property : {{fullName}}</h3>

    </div>
</template>

<script setup>
//  with out reactivity

import { ref ,reactive ,computed} from 'vue';

let fName = ref('main');
let lName = ref('user');

const newFun=(roll)=> {
    return fName.value+roll + " , " + lName.value+roll
}

const fullName=computed(()=> {
    return fName.value + " , " + lName.value + " , " + "from computed prperty"
})


setTimeout(() => {
    lName.value = "user 1 ,"
}, 3000);

const newFunc1 = ()=> {
   console.log("called");
}

newFunc1();



</script>

<style  scoped></style>