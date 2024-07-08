<script setup="ts">

const props = defineProps({
    title: String,
    value: Number,
    count: Number
})
defineEmits(['plusFour', 'plusThree','plusTwo','plusOne'])

</script>


<template>
    <button v-if="value==4 && count==20" @click="$emit('plusFour')" class = "bg-purple-700 hover:bg-purple-500 rounded-lg shadow-md px-3 py-3">
        {{ title }}
    </button>
    <button v-else-if="value==3 && count>10" @click="$emit('plusThree')" class = "bg-violet-700 hover:bg-violet-500 rounded-lg shadow-md px-3 py-3">
        {{ title }}
    </button>
    <button v-else-if="value==2 && count>4" @click="$emit('plusTwo')" class = "bg-indigo-700 hover:bg-indigo-500 rounded-lg shadow-md px-3 py-3">
        {{ title }}
    </button>
    <button v-else-if="value==1 && count>0" @click="$emit('plusOne')" class = "bg-blue-700 hover:bg-blue-500 rounded-lg shadow-md px-3 py-3">
        {{ title }}
    </button>
</template>