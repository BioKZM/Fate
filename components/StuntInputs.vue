<script setup = "ts">



const items = reactive([])
var uIndex = ref(0)
function addStunt()
{
    if (items.length < 6)
    {

        items.push(uIndex.value++)
    }

}
function deleteStunt(index)
{
    const idx = items.indexOf(items)
    items.splice(idx,1)
}
</script>


<template>
    <div class = "grid justify-center justify-items-center">
        <div class ="text-2xl py-5">
        Stunts 
        </div>
        <div v-for="(,index) in items" :key="index" class = "py-2 text-black " >
            <TextArea :count="'stuntArea'+index"/>
            
        </div>
        <div class = "justify-between">
            <AddStunt @addStunt="addStunt"/>
            <DeleteStunt @deleteStunt = "deleteStunt(index)" />
        </div>
    </div>
</template>

<style>
</style>