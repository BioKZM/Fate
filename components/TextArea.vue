<script setup="ts">
const props=defineProps(
    {
        count:String,
    }
)
</script>

<template>

    
    <textarea v-if="count == 'sheetArea0'" :id = "count" class = "rounded-lg px-5 py-5 resize-none bg-zinc-700 text-white" rows="1" cols="100"/>
    <textarea v-else :id = "count" class = "rounded-lg px-5 py-5 resize-none bg-zinc-700 text-white" rows="7" cols="100"/>

</template>