<template>
    <div>
      i am template ref child
      <div>
        <label for="username">User Name</label>
        <input type="text" id="username" ref="inputRef" >
      </div>
    </div>
</template>

<script setup>
import { ref , onMounted } from 'vue';
const inputRef = ref(null);

onMounted(() => {
    console.log(inputRef.value);
    
})

</script>

<style lang="scss" scoped>

</style>