<template>
    <div>
        <h1> click count is : {{ count }}</h1>
        <button v-on:click="count = count + 1">Increase</button>
        <!-- <button v-on:click="count = count - 1" >Decrease</button>
        <button @click="count = count + 1" >Increase</button> -->
        <button @click="count = count - 1">Decrease</button>
        <br>
        <button @click="eventMethod('201')">for arrow function</button>
        <button @click="newMethod('naim')">for normal function</button>
        <button @click="methodHandler">Event method handler</button>

        <!-- event hander with predent default -->
        <a @click.prevent="modifierHandler" href="https://www.cricbuzz.com/">Event method handler</a>

        <form @submit.prevent="formSubmit">
            <button type="submit"> Submit </button>
        </form>
        <br>
        <!-- key modifier with enter key -->
        <input type="text" @keyup.enter="keyModifierEnter">
        <br>
        <!-- system modifier with alt + enter key -->
        <input type="text" @keyup.alt.enter="systemModifierAltEnter">
        <br>
        <br>
        <!-- multiple mouse event -->
        <button v-on="{ mousedown: mouseDawn, mouseup: mouseUp }"> mouseup and dawn </button> 
        <br>
        <br>
        <!-- multiple mouse event with one clik  -->
        <button @click="firstEvent() , secondEvent() , thirdEvent()"> multiple methood call with one clik</button> 

    </div>
</template>

<script setup>
import { ref } from "vue";
let count = ref(0);

// methos calling from event arrow function

const eventMethod = (val) => {
    console.log("from method arrow function call" + " " + val);
}
// const eventMethod = ()=>{
//     console.log("from method arrow function call");
// }

//  for normal function call

// function newMethod(val){
//     console.log("i am  from new normal function" + " " + val);
// }

function newMethod(name) {
    console.log(name);
}

function methodHandler(e) {
    console.log("event", e);
}

// event modifier

function modifierHandler() {

    console.log(" i am from event modifier");
}

// form submit with event handler

const formSubmit = () => {

    console.log("form submited");
}

// key modifier

const keyModifierEnter = () => {
    console.log(" Enter key pressed");
}

// system modifier

const systemModifierAltEnter = () => {
    console.log("i am from system modifer with alt + enter key press");
}

// mutiple mouse event
const mouseUp = () => {
    console.log(" mouse up pressed");
}
const mouseDawn = () => {
    console.log(" mouse dawn pressed");
}
const firstEvent = () => {
    console.log(" first event pressed");
}
const secondEvent = () => {
    console.log(" second event pressed");
}
const thirdEvent = () => {
    console.log(" third pressed");
}


</script>

<style scoped></style>