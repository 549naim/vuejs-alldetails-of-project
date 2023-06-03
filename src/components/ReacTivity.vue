<template>
    <div>
      <!-- SUM is {{ number.a + number.b }} -->

      click count : {{object.num.count}}
      <br>
      all User : {{object.user}}
    </div>
</template>

<script setup>
import { reactive } from 'vue';
//   let number ={
//     a:10,b:20
//   };
//   setTimeout(()=> {
//      console.log("set Time Out called");
//      console.log("Number" , number);
//      number.a = 50;
//      console.log("A" , number.a);
//   },3000);

//   let number =reactive({
//     a:10,b:20
//   });
//   setTimeout(()=> {
//      console.log("set Time Out called");
//      console.log("Number" , number);
//      number.a = 50;
//      console.log("A" , number.a);
//   },3000)

// let number =reactive({count:0}) ;
// setTimeout(() => {
//    console.log("time out called");
//    console.log(number);
//    number.count=number.count +1
//    console.log("count :" , number.count); 
// }, 3000);


let object =reactive({
    num:{
        count:0,
    },
    user:["user a", "user b"],
})

// setTimeout(() => {
//     console.log("timeout called");
//     console.log("Object :" , object );
//     console.log("Object Num :" , object.num );
//     console.log("Object Num count:" , object.num.count );
//     console.log("Object user:" , object.user );
//     console.log("reactivity called");
//     object.num.count = object.num.count + 1;
//     object.user.push( "user c", "user d", "user e");
//     console.log("Object user:" , object.user );
//     console.log("Object num:" , object.num );
// }, 3000);


</script>

<style lang="scss" scoped>

</style>