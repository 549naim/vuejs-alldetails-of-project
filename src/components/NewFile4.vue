<template>
    <div>
      <h3>{{newid}}</h3>
      <h3 v-bind:id="newid">Hellow</h3>
      <h3 :id="newid1" :href="url">Hellow2</h3>
      <a v-bind="object">visit</a>
      <a v-bind:[newhref] = "url">visit 1</a>
<br>
<br>
      <button v-bind:disabled="isDisable" >click me</button>
    </div>
</template>

<script setup>
    
    let newid = "naim";
    let newid1 = "naim";
    let url = "http://google.com";
    let object = {
        id:"newid2",
        href:"http://google.com",
        class:"newclass",
    };
    let newhref = "href";
    let isDisable = false;

    
</script>

<style scoped>

#naim{
    background-color: rgb(0, 255, 13);
    color: rgb(255, 63, 63);
    
}

#naim:hover{
    background-color:blue;
    color: white;
}
#newid2{
    background-color:red;
    color: black;
}
.newclass:hover{
    font-size:100px;
    
}

</style>