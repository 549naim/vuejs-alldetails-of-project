<template>
    <div>
       <!-- prop validation -->
      <h1 class="title"> First Name : {{firstName}}</h1>
      <h1 class="title"> Last Name : {{lastName}}</h1>
      <h1 class="title"> Full Name Name : {{fullName}}</h1>
      <h1 class="title"> Full Name and age : {{age}}</h1>
      <!-- from object -->
      <h1 class="title"> Full Name and city : {{city}} , {{name}}</h1>

      <!-- using custom class -->

      <!--  from exported person class -->
       <h1> from exported person class : {{author?.fName}} , {{author?.lName}}</h1>
    </div>
</template>

<script setup>
import { computed } from "vue";
import { Person } from "../service/Porson";
const prop = defineProps({
    firstName:String,
    lastName:String,
    age:Number,
    // these are from  prop object
    name:String,
    city:String,
    author:Person,
}


);
// using computed property for auto update

const fullName = computed(()=>prop.firstName + " " + prop.lastName);

// custom class


</script>

<style lang="scss" scoped>

</style>