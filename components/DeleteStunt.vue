<script setup="ts">
defineEmits(['deleteStunt'])
</script>

<template>
    <button  @click="$emit('deleteStunt')" class = "bg-red-800 hover:bg-red-700 rounded-lg shadow-md px-2 py-2 mx-2 text-white ">Delete</button>
</template>