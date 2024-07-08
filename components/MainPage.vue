<script setup = "ts">
import NavBar from './NavBar.vue'
import CharacterSheet from './CharacterSheet.vue'
</script>

<template>
    <NavBar/>
    <CharacterSheet/>
    <StuntInputs/>
    <SkillDiv/>
    <Canvas/>
</template>

<style>
    html
    {
        width: 100%;
        background-color: #242424;
        --tw-text-opacity: 1;
        color: rgb(255 255 255 / var(--tw-text-opacity));
        padding-bottom:100px;
    }

</style>