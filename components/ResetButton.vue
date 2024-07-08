<script setup="ts">

var emits = defineEmits(["resetSkills"])
</script>


<template>
    <button @click="$emit('resetSkills')" class = "rounded-lg shadow-md py-3 px-3 bg-red-800 hover:bg-red-700">Reset</button>
</template>