<script setup="ts">
    var buttonID = ref(0)
    var items = ref(
        [
        {
            title: "Akademik",
            value: 0
        },
        {
            title: "Aldatmaca",
            value: 0
        },
        {
            title: "Atıcılık",
            value: 0
        },
        {
            title: "Bağlantılar",
            value: 0
        },
        {
            title: "Beden",
            value: 0
        },
        {
            title: "Çeviklik",
            value: 0
        },
        {
            title: "Empati",
            value: 0
        },
        {
            title: "Farkındalık",
            value: 0
        },
        {
            title: "Gizlilik",
            value: 0
        },
        {
            title: "Gözlem",
            value: 0
        },
        {
            title: "Hırsızlık",
            value: 0
        },
        {
            title: "İlim",
            value: 0
        },
        {
            title: "İrade",
            value: 0
        },
        {
            title: "Kaynaklar",
            value: 0
        },
        {
            title: "Kışkırtma",
            value: 0
        },
        {
            title: "Muhabbet",
            value: 0
        },
        {
            title: "Sürücülük",
            value: 0
        },
        {
            title: "Yakın Dövüş",
            value: 0
        },
        {
            title: "Zanaat",
            value: 0
        },
    ]
    )
    const buttonItems = ref([
    {
        title:"+4",
        value: 4,
        count: 1
    },
    {
        title:"+3",
        value: 3,
        count: 2
    },
    {
        title:"+2",
        value: 2,
        count: 3,
    },
    {
        title:"+1",
        value: 1,
        count: 4
    },

    ])
    var skillPointCount = ref(20)

    function plusFour(index)
    {
        items.value[index].value = 4
        skillPointCount.value -= 4
        console.log(skillPointCount.value)
    }
    function plusThree(index)
    {
        items.value[index].value = 3
        skillPointCount.value -= 3
        console.log(skillPointCount.value)
    }
    function plusTwo(index)
    {
        items.value[index].value = 2
        skillPointCount.value -= 2
        console.log(skillPointCount.value)
    }
    function plusOne(index)
    {
        items.value[index].value = 1
        skillPointCount.value -= 1
        console.log(skillPointCount.value)
    }
    function resetSkills()
    {
        for (var x=0; x<19; x++)
        {
            items.value[x].value = 0

        }
        skillPointCount.value = 20
    }
    

</script>

<template>
    <div v-for="(item,index) in items" class = "py-2 px-2 flex items-center justify-between">
        <div>
            {{ item.title }}: 
        </div>

        <div class = "px-2">
            <SkillPoint :value="item.value" :id="index"/>
            <LevelButton v-for="item in buttonItems" :title="item.title" :value = "item.value" :id ="buttonID" :count="skillPointCount" @plusFour="plusFour(index)" @plusThree="plusThree(index)" @plusTwo="plusTwo(index)" @plusOne="plusOne(index)" class = "mx-2"/>
        </div>
        
    </div>
    <div class = "py-5 px-2 flex items-center justify-center">
         <ResetButton @resetSkills="resetSkills" />
    </div>
</template>