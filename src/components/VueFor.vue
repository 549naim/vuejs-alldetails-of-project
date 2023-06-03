<template>
    <div>
 <h1> i ma from v for </h1>
 <div>
    <p>array of strings</p>
    <h1 v-for="(student,i) in students" :key="i"> student name is :{{ i }}  {{student}}</h1>

 </div>

 <div>
    <p>array of strings ( without array keys )</p>
    <h1 v-for="student in students"> student name is :  {{student}}</h1>

 </div>

 <div>
    <p>array of objects</p>
    <h1 v-for="(user,i) in users" :key="i"> user name is : {{user.name}} : {{user.salary}} : {{user.age}}</h1>
 </div>
 
 <div>
    <p>array of objects ( object distructoring )</p>
    <h1 v-for="({name , salary , age},i) in users" :key="i"> user name is : {{name}} : {{salary}} : {{age}}</h1>
 </div>
 

 <div>
    <h3>this is for nasted array </h3>
    <div v-for="(lang , i) in languages" :key="i" >
      
      <h1 v-for="(item , index) in lang" :key="index" > this is language <span class="index"> {{ i }}</span> <span class="lang">   {{ index }} {{ item }} </span> </h1>
      <p>finish</p> 
      
    </div>
 </div>

 
 <div>
    <p> for loop in plane object</p>
    <h2 v-for="(key , value , index) in course" :key="index" > {{ index }} this is for course :<span class="index" > {{ key }} </span>  : <span class="lang" > {{ value }} </span></h2>
 </div>

<div>
    <p>for loop in nasted object</p>
    <div v-for="type in nastedObject" :key="type.id" >
    <!-- <div v-for="(type , key) in nastedObject" :key="type.id" > -->
    <!-- <div v-for="{id , name ,age , subject} in nastedObject" :key="id" > -->
         <!-- <h1> <span class="grand"> {{name}} </span>: <span class="lang">{{age}}</span> : <span class="parent"> {{subject}} </span>: <span class="child"> {{id}}</span></h1>
         <hr> -->
        <!-- <h1 v-for="(item,newKey) in type" >Grand Parent Obj <span class="grand" >{{key}}</span>  : parent obj <span class="parent">  {{ newKey }}</span> : child obj <span class="child">  {{item}} </span>  </h1> -->
        <h1 v-for="(item,newKey) in type" > (key) <span class="grand" >{{newKey}}</span>  : (value) <span class="parent">  {{ item }}</span>  </h1>
        
        <hr>
        
    </div>
   

</div>

<div>
    use of v-for and v-if
    <div v-for="( {name , id , age , subject}, i) in nastedObject"  :key="i" >
        <h1 v-if="age > 10 " > {{name}} : {{age}} : {{subject}} : {{id}}</h1>

    </div>

    
</div>

<div>
    use of v-for and v-if with computed properties
    <div v-for="( {name , salary , age }, i) in comIfUser"  :key="i" >
        <h1 class="parent" > {{name}} : {{age}} : {{salary}} </h1>

    </div>

    
</div>

<div>
    use of v-for and v-if with method 
    <div v-for="( {name , salary , age }, i) in methodIfUser(users)"  :key="i" >
        <h1 class="lang" > {{name}} : {{age}} : {{salary}} </h1>

    </div>

    
</div>

<hr>
  <ForloopCom v-for="( employee, i) in methodIfUser(users)" :key="i"  :user = "employee" />

  <h1>{{course}}</h1>

    </div>
</template>

<script setup>
import {ref , reactive ,computed} from 'vue';
import ForloopCom from './ForloopCom.vue';
// array of strings
const students = ref(["student 1 ","student 2 ","student 3 ","student 4 ","student 5"]);
// array of objects
const users = ref([
    {name: "user 1" , salary: 100 , age: "30" },
    {name: "user 2" , salary: 200 , age: "31" },
    {name: "user 3" , salary: 300 , age: "32" },
    {name: "user 4" , salary: 400 , age: "33" },
]);

//  nasted array
const languages = ref(
    [
        ["java" , "android"],
        ["php" , "web"],
        [" dot net" , "os"],
        ["dart" , "flutter"],
    ]
);

// for loop in plane object

const course = reactive(
    {
        javascript : "web",
        python : "ML",
        dot_net : "OS",
        dart : "Flutter",
    }
);

// nasted object

let nastedObject = reactive(
    {
       teacher :{
        id : 1,
        name : "teacher 1",
        age : 30,
        subject : "math",
       },
       student :{
        id : 2,
        name : "student 1",
        age : 10,
        subject : "eng",
       },
       gurdian :{
        id : 3,
        name : "gurduan 1",
        age :40,
        subject : "bangla",
       }
    }
);

// filter data with computed property and condition

const comIfUser = computed(()=>{
    return users.value.filter((person)=>person.salary > 100);
});


// filter data with method and condition

function methodIfUser(user) {
    return user.filter((person)=>person.salary >= 200);
}


</script>

<style  scoped>
 .lang {
    background-color: aqua;
 }
 .index{
    background-color:rgb(255, 245, 63);
 }
 .grand{
    background-color:rgb(63, 255, 85);
 }
 .parent{
    background-color:rgb(223, 63, 255);
 }
 .child{
    background-color:rgb(255, 143, 63);
 }
 
</style>