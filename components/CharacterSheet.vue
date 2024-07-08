<script setup = "ts">
import CharacterSheetInput from '../components/CharacterSheetInputs.vue'


const items = ref(["Character Name","High Concept", "Trouble","Relationship","Free Aspect 1", "Free Aspect 2"])


</script>

<template>
    <div v-for="(item,index) in items" :key="index">
        <CharacterSheetInput :title="item" :count = "'sheetArea'+index"/>
    </div>
</template>