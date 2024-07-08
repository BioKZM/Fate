<script setup="ts">
const props = defineProps(
    {
        id: Number,
        value: Number
    }
)
</script>

<template>
    <button :id = "id" class = "bg-zinc-700 text-lg text-white px-4 py-2 rounded-lg mx-10 border-zinc-600 border-x-4 border-y-4" disabled>{{value}}</button>
</template>