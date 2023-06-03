<template>
    <div>
        <h2>i am from vue form</h2>
        <pre>{{ data }} </pre>

        <form @submit.prevent="handleForm">
            <div>
                <label for="name">Name : </label>
                <input v-model="data.fullname" type="text" id="name">
            </div>
            <br>
            <div>
                <label for="email">Email : </label>
                <input v-model="data.email" type="email" id="email">
            </div>
            <br>
            <div>
                <label for="password">Password : </label>
                <input v-model="data.password" type="password" id="password">
            </div>
            <br>
            <div>
                <label for="message">Message : </label>
                <textarea rows="3" v-model="data.message" id="message"> </textarea>
            </div>
            <br>
            <div>
                <label for="checkbox">Checkbox : </label>
                <input v-model="data.checkbox" type="checkbox" id="checkbox">
            </div>
            <br>
            <div>
                <label for="married">Married : </label>
                <input v-model="data.married" type="checkbox" id="married" true-value="Yes" false-value="No">
            </div>
            <br>
            <div>
                <h5>Language :</h5>
                <label for="python">Python : </label>
                <input v-model="data.languages" type="checkbox" id="python" value="python">
                <label for="php">php : </label>
                <input v-model="data.languages" type="checkbox" id="php" value="php">
                <label for="js">js : </label>
                <input v-model="data.languages" type="checkbox" id="js" value="js">
            </div>
            <br>
            <div>
                <h5>Gender :</h5>
                <label for="male">Male : </label>
                <input v-model="data.gender" type="radio" id="male" value="male">
                <label for="female">Female : </label>
                <input v-model="data.gender" type="radio" id="female" value="female">

            </div>
            <br>
            <div>
                <label for="select">Framework : </label>
                <select v-model="data.framework" id="select">
                    <option disabled value="">---select one ---</option>
                    <option>Laravel</option>
                    <option>Django</option>
                    <option>Node Js</option>
                </select>
            </div>
            <br>

            <div>
                <label for="city">City : </label>
                <select v-model="data.city" id="city" multiple >           
                    <option>Dhaka</option>
                    <option>khulna</option>
                    <option>Rajshahi</option>
                </select>
            </div>
            <br>

            <div>
                <label for="country">Country : </label>
                <select v-model="data.country" id="country" >           
                    <option v-for="c in countries" :value="c.value" >{{c.name}}</option>
                   
                </select>
            </div>
            <br>

            <button type="submit">Form Submit</button>

        </form>



    </div>
</template>

<script setup>
import { ref, reactive } from 'vue'

const data = reactive({
    fullname: "",
    email: "",
    password: "",
    message: "",
    checkbox: false,
    married: "No",
    languages: [],
    gender: "",
    framework: "",
    city: [],
    country: "",
});
const countries = ref([
    {name: "USA" , value: "USA"},
    {name: "Canada" , value: "Canada"},
    {name: "Mexico" , value: "Mexico"},
    {name: "Italy" , value: "Italy"},
    {name: "Finland" , value: "Finland"},
]);
// let fullname = ref("");


function handleForm() {
    console.log("Form submitted", data);
}

</script>

<style lang="scss" scoped></style>