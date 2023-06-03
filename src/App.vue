<script setup >
import IfCom1 from './components/IfCom1.vue';
import IfCom2 from './components/IfCom2.vue';
import NewFile1 from './components/NewFile1.vue'
import NewFile3 from './components/NewFile3.vue'
import NewFile4 from './components/NewFile4.vue'
import PropVal from './components/PropVal.vue';
import ReacTivity from './components/ReacTivity.vue';
import ReactUti from './components/ReactUti.vue';
import UseRef from './components/UseRef.vue';
import VueEvent from './components/VueEvent.vue';
import VueFor from './components/VueFor.vue';
import VueForm from './components/VueForm.vue';
import VueIf from './components/VueIf.vue';
import { ref, reactive } from "vue";
import { Person } from './service/Porson';
import ComEvent from './components/ComEvent.vue';
import VueSlot from './components/VueSlot.vue';
import SlotCom from './components/SlotCom.vue';
import ProInject from './components/ProInject.vue';
import { provide } from 'vue';
import LifeCycle from './components/LifeCycle.vue';
import { onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUnmounted, onUpdated } from 'vue'
import VueWatchers from './components/VueWatchers.vue';
import TempRefParent from './components/TempRefParent.vue';
import AsyncParent from './components/AsyncParent.vue';
import DynamicComponent from './components/DynamicComponent.vue';
import ImageVue from './components/ImageVue.vue';
import ApiCall from './components/ApiCall.vue';
const person = new Person("naim", "rakibul");

const name = "duosoft"

let vuecom = ref(2);

let firstName = ref("Rakibul")
let lastName = ref("Naim")
let age = ref(24)

let newObj = reactive({
  name: "rk naim",
  city: "dhaka",
}
);

const newCount = ref(0);

function increaseBy() {
  newCount.value = newCount.value + 1;
  console.log("increase ny one");
}

function increaseWithArgs(n, str) {
  newCount.value = newCount.value + n;
  console.log("increase ny one" + " " + str);
}

// event validation
function newFormSubmit(name1) {

  console.log("form submited", name1);
}

provide("myName", "rakibul");
// provide object  
provide("course", {
  name: "react",
  duration: "15 hrs",
  fees: 1000,
}

);

// provide reactive state

const cost = ref(100000);

provide("cost", cost);



// for lifecycle hooks
const showHide = ref(true);
const count = ref(0);

onBeforeMount(() => {
  console.log("i Am from onBeforeMount from ----- Parent");
})

onBeforeUnmount(() => {
  console.log("i Am from onBeforeUnmount from ----- Parent");
})

onBeforeUpdate(() => {
  console.log("i Am from onBeforeUpdate from ----- Parent");
})

onMounted(() => {
  console.log("i Am from onMounted from ----- Parent");
})

onUnmounted(() => {
  console.log("i Am from onUnmounted from ----- Parent");
});

onUpdated(() => {
  console.log("i Am from onUpdated from ----- Parent");
})

</script>

<template>
  <div>
    <h1>Local registration by {{ name }}</h1>

    <p>hey</p>

    <NewFile1 />
    <hr>
    <NewFile3 />
    <hr>
    <NewFile4 />
    <hr>
    <ReacTivity />
    <hr>
    <UseRef />
    <hr>
    <ReactUti />
    <hr>
    <VueIf />

    <hr>

    <IfCom1 v-if="vuecom === 1" />
    <IfCom2 v-if="vuecom === 2" />
    <hr>
    <VueFor />

    <hr>

    <VueEvent />

    <hr>
    <VueForm />
    <hr>
    <!-- prop validation -->
    <!-- <PropVal name="Naim" />
    <PropVal name="rakibul" />
    <PropVal name="islam" />
    <PropVal name="maria" /> -->
    <!-- static prop -->


    <PropVal :firstName="firstName" :lastName="lastName" :age="age" v-bind="newObj" :author="person" />

    <!-- passing object as props we can use these type ( :name="newObj.name" :city="newObj.city" )  -->

    <hr>
    <!-- <h1> Count : {{ newCount }}</h1> -->
    <!-- <ComEvent @countIncrease = "newCount++"/> -->
    <!-- <ComEvent @countIncrease = "increaseBy"/> -->


    <!--increase with argument <ComEvent @countIncrease = "increaseWithArgs"/> -->

    <!-- event validation -->
    <ComEvent @formSubmit="newFormSubmit" />

    <hr>
    <!-- <VueSlot><h1>{{lastName}}</h1></VueSlot>
   <VueSlot><h3>{{firstName}}</h3></VueSlot> -->

    <!-- it can use as shorthand with #header -->
    <VueSlot>
      <template v-slot:header>

        <h1>I am slot header </h1>
        <SlotCom />

      </template>
      <template v-slot:footer>

        <h1> <sup> I am slot footer </sup></h1>

      </template>
    </VueSlot>
    <hr>
    <p>inject and service provider</p>
    <h3>app</h3>
    <!-- usiing props -->
    <!-- <ProInject name="Naim" /> -->
    <ProInject />
    <hr>
    <div class="lifecycle">
      <h2>i am from lifecycle hooks</h2>
      <LifeCycle v-if="showHide" />
      <button @click="showHide = !showHide">show/hide</button>
      <h3>count : {{ count }}</h3>
      <button @click="count++">increase</button>
    </div>
    <hr>
    <VueWatchers />
    <hr>
    <TempRefParent />
    <hr>
    <AsyncParent />
    <hr>
    <DynamicComponent />
    <hr>
    <ImageVue />
    <hr>
    <ApiCall/>
  </div>
</template>

<style scoped>
h1 {
  background-color: aqua;

}

.lifecycle {
  background-color: rgb(58, 111, 204);
}
</style>