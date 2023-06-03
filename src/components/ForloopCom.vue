<template>
    <div>
    <h3>i am from for loop component {{user?.name}} , {{user?.salary}}</h3>

    </div>
</template>

<script setup>
defineProps({
    user:Object,
});

</script>

<style lang="scss" scoped>

</style>