<script setup = "ts">
const props = defineProps({
    title:String,
    count:String

})



</script>

<template>
    <div class = "text-2xl py-5 grid justify-center">
        {{ title }}
    </div>
    <div class = "text-black grid justify-center">
        <TextArea :count="count"/>
    </div>
</template>

<style>

</style>