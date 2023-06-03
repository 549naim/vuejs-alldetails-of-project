<template>
    <div>
       
      <h1>hellow from --- child</h1>
    </div>
</template>

<script setup>

import { onBeforeMount ,onBeforeUnmount ,onBeforeUpdate , onMounted, onUnmounted , onUpdated} from 'vue'
onBeforeMount(() => {
  console.log("i Am from onBeforeMount from ----- Child");
})

onBeforeUnmount(() => {
  console.log("i Am from onBeforeUnmount from ----- Child");
})

onBeforeUpdate(() => {
  console.log("i Am from onBeforeUpdate from ----- Child");
})

onMounted(() => {
  console.log("i Am from onMounted from ----- Child");
})

onUnmounted(() => {
  console.log("i Am from onUnmounted from ----- Child");
});

onUpdated(() => {
  console.log("i Am from onUpdated from ----- Child");
})

</script>

<style lang="scss" scoped>

</style>