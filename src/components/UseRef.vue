<template>
    <div>
       
        <h1>i am from use ref :  {{+ 5}}</h1>

    </div>
</template>

<script setup>
import { ref ,reactive} from 'vue';
// let a = ref(10);
// let b = ref(20);
// setTimeout(() => {
//     console.log("a", a);
//     console.log("b", b);
//     a.value = 30;
//     console.log("a", a.value);
//     console.log("b", b.value);
// }, 3000);

// let obj1 = ref({count:0});
// setTimeout(() => {
//     obj1.value.count = 1 ;
//     console.log("obj 1" ,obj1);
//     console.log("obj 1 value" ,obj1.value);
//     console.log("obj 1 value count" ,obj1.value.count);
// }, 3000);

// let obj2 = {count:ref(0),count2:ref(10)};
// setTimeout(() => {
//     obj2.count.value = 1 ;
//     console.log("obj 1" ,obj2);
//     console.log("obj 1 value" ,obj2.count);
//     console.log("obj 1 value count" ,obj2.count.value);
// }, 3000);
// let {count2 }= obj2

 const obj = reactive([ref("user 1") , ref("user 2")])
 console.log(obj);
 console.log(obj[0].value);
 console.log(obj[0]);
 console.log(obj[1].value);
 console.log(obj[1]);
 obj.push(ref("user 3"));
 console.log(obj);


</script>

<style scoped></style>
