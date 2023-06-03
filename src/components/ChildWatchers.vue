<template>
    <div>
        <div class="heartrate">
<!--  with single ref  -->
        <!--  
             <h1>Heart rate tracking </h1>
        <h2 v-if="heartBeat > 0" >Heart rate per minute is : {{heartBeat}}</h2>
        <h2 v-if="heartBeat <= 0" > Sorry bro you dead >>>>>>>>>>>>>>></h2>
        <button @click="heartBeat= heartBeat+10"  >Increase</button> <button @click="heartBeat= heartBeat-10">Descrease</button> -->

        <!--  with reactive object -->

        <!-- <h1>Heart rate tracking </h1>
        <h2 v-if="stateData.heartBeat > 0" >Heart rate per minute is : {{stateData.heartBeat}}</h2>
        <h2 v-if="stateData.heartBeat <= 0" > Sorry bro you dead >>>>>>>>>>>>>>></h2>
        <button @click="stateData.heartBeat= stateData.heartBeat+10"  >Increase</button> <button @click="stateData.heartBeat= stateData.heartBeat-10">Descrease</button> -->

        <h1>Heart rate tracking </h1>
        <h2 v-if="heartBeat > 0" >Heart rate per minute is : {{heartBeat}}</h2>
        <h2 v-if="heartBeat <= 0" > Sorry bro you dead >>>>>>>>>>>>>>></h2>
        <h2  >  >>>>>>>Fear :  {{ fear }}>>>>>>>></h2>
        <button @click="heartBeat= heartBeat+10"  >Increase</button> <button @click="heartBeat= heartBeat-10">Descrease</button>


    </div>
    </div>
</template>

<script setup>
import { ref, watch ,reactive } from 'vue';


const heartBeat = ref(0);
const fear = ref(10);
// watchers in single ref
// watch(heartBeat,(newheartRate,oldheartRate)=>{
//      console.log("New heart rate: " + newheartRate );
//      console.log("Old heart rate: " + oldheartRate );
//      if (newheartRate >= 120 && newheartRate > oldheartRate) {
//         alert("please calm dawn ... your heart rate is increasing");
//      }
// });


//  watchers with reactive object
// const stateData = reactive({heartBeat:85}) 
//  in object stateData.heartBeat will not acces th e data
//  we have to use whole object stateData
// watch(stateData,(newheartRate,oldheartRate)=>{
//      console.log("New heart rate: " , newheartRate );
//      console.log("Old heart rate: " , oldheartRate );
//      if (newheartRate.heartBeat >= 120 ) {
//         alert("please calm dawn ... your heart rate is increasing");
//      }
// });

// using getter function
// watch(()=>stateData.heartBeat,(newheartRate,oldheartRate)=>{
//      console.log("New heart rate: " , newheartRate );
//      console.log("Old heart rate: " , oldheartRate );
//      if (newheartRate >= 120  && newheartRate > oldheartRate ) {
//         alert("please calm dawn ... your heart rate is increasing");
//      }
// });

// using getter function and multiple attribute of object
// watch(()=>{
//     return {...stateData}
// },(newheartRate,oldheartRate)=>{
//      console.log("New heart rate: " , newheartRate.heartBeat );
//      console.log("Old heart rate: " , oldheartRate.heartBeat );
//      if (newheartRate.heartBeat >= 120  && newheartRate.heartBeat > oldheartRate.heartBeat ) {
//         alert("please calm dawn ... your heart rate is increasing");
//      }
// });

// watchers in multi  single ref
watch([heartBeat ,fear],(newheartRate,oldheartRate)=>{
     console.log("New heart rate: " , newheartRate[0]);
     console.log("Old heart rate: " , oldheartRate[0] );

     console.log("New fear rate: " , newheartRate[1]);
     console.log("Old fear rate: " , oldheartRate[1] );
    //  if (newheartRate >= 120 && newheartRate > oldheartRate) {
    //     alert("please calm dawn ... your heart rate is increasing");
    //  }
});


</script>

<style lang="css" scoped>
.heartrate{
    background-color:yellowgreen;
    padding: 10px;
   text-align: center;
}
</style>