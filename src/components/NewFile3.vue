
<template>
    <div>
       <h2>this is from newfile 3</h2>
       <h3>{{num*3}}</h3>
       <h3>{{10 + 20}}</h3>
       <h2>
        {{ newFunction() }}
        {{ sun? "Dark" : "Sunshine" }}
    </h2>
    </div>
</template>

<script setup>
  let num = 50;
  let name = ""
  let sun =false;
  function newFunction() {
    return name = " Dusoft"
  }
</script>

<style lang="scss" scoped>

</style>