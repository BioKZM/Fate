<script setup="ts">
defineEmits(['addStunt'])
</script>

<template>
    <button @click="$emit('addStunt')" class = "bg-sky-700 px-2 py-2 rounded-lg shadow-md hover:bg-sky-600 ">
        Add Stunt
    </button>
</template>