<script setup>



var dummyArray = [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18]
var skillArray = ["Akademik","Aldatmaca","Atıcılık","Bağlantılar","Beden","Çeviklik","Empati","Farkındalık","Gizlilik","Gözlem","Hırsızlık","İlim","İrade","Kaynaklar","Kışkırtma","Muhabbet","Sürücülük","Yakın Dövüş","Zanaat"]


function createSheet(selection)
{
    
    var c = document.getElementById("sheetCanvas")
    var ctx = c.getContext("2d")
    

    if (selection == 0)
    {
        var mijasaPNG = new Image();
        mijasaPNG.src = 'assets/assets/mijasa.png';
        console.log(mijasaPNG)
        mijasaPNG.onload = function()
        {
            ctx.drawImage(mijasaPNG, 473, 1400,427,579);
        }
        ctx.fillStyle="#FFFFFF"
        ctx.fillRect(0,0,946,1920)

        ctx.fillStyle="#000000"
        
        var name = document.getElementById("sheetArea0")
        var highConcept = document.getElementById("sheetArea1")
        var trouble = document.getElementById("sheetArea2")
        var relationship = document.getElementById("sheetArea3")
        var freeAspect1 = document.getElementById("sheetArea4")
        var freeAspect2 = document.getElementById("sheetArea5")
    

        
        ctx.font = "25px Arial"
        ctx.fillText("Character Name", 30,100)
        ctx.fillText("High Concept", 30, 250)
        ctx.fillText("Trouble",30,400)
        ctx.fillText("Relationship",30,550)
        ctx.fillText("Free Aspect 1 ",30,700)
        ctx.fillText("Free Aspect 2 ",30,850)
        ctx.fillText("Stunt 1",30,1000)
        ctx.fillText("Stunt 2",30,1150)
        ctx.fillText("Stunt 3",30,1300)
        ctx.fillText("Stunt 4",30,1450)
        ctx.fillText("Stunt 5",30,1600)
        ctx.fillText("Stunt 6",30,1750)

        ctx.font = "15px Arial"
        cropText(ctx,name,130)
        cropText(ctx,highConcept,280)
        cropText(ctx,trouble,430)
        cropText(ctx,relationship,580)
        cropText(ctx,freeAspect1,730)
        cropText(ctx,freeAspect2,880)



        if (document.getElementById("stuntArea0") != null)
        {
            var stunt1 = document.getElementById("stuntArea0")
            cropText(ctx,stunt1,1030)

        }
        if (document.getElementById("stuntArea1") != null)
        {
            var stunt2 = document.getElementById("stuntArea1")
            cropText(ctx,stunt2,1180)
            
        }   
        if (document.getElementById("stuntArea2") != null)
        {
            var stunt3 = document.getElementById("stuntArea2")
            cropText(ctx,stunt3,1330)
            
        }   
        if (document.getElementById("stuntArea3") != null)
        {
            var stunt4 = document.getElementById("stuntArea3")
            cropText(ctx,stunt4,1480)

        }   
        if (document.getElementById("stuntArea4") != null)
        {
            var stunt5 = document.getElementById("stuntArea4")
            cropText(ctx,stunt5,1630)
            
        }   
        if (document.getElementById("stuntArea5") != null)
        {
            var stunt6 = document.getElementById("stuntArea5")
            cropText(ctx,stunt6,1780)
            
        }   



        ctx.moveTo(473,0)
        ctx.lineTo(473,1920)
        ctx.stroke()
        var countX = 550
        var countY = 100
        ctx.font = "30px Arial"
        for (var x in dummyArray)
        {
            var skillValue = document.getElementById(x).innerHTML
            ctx.fillText(skillArray[x],countX,countY)
            ctx.fillText(skillValue,countX+200,countY)
            countY+=70
        }
        ctx.font = "30px Arial"
        ctx.fillStyle="#000000"
        ctx.fillRect(0,0,473,50)

        ctx.fillStyle="#FFFFFF"
        ctx.fillText("Aspects",180,40)

        ctx.fillStyle="#000000"
        ctx.fillRect(473,0,473,50)
        
        ctx.fillStyle="#FFFFFF"
        ctx.fillText("Skills",670,40)

        var downloadButton = document.getElementById("downloadButton")
        downloadButton.disabled=false
        downloadButton.classList.remove("bg-gray-700")
        downloadButton.classList.add("bg-blue-800")
        downloadButton.classList.add("hover:bg-blue-700")
    }
    
    else
    {
        ctx.clearRect(0,0,c.width,c.height)
        var downloadButton = document.getElementById("downloadButton")
        downloadButton.disabled=true
        downloadButton.classList.remove("bg-blue-800")
        downloadButton.classList.remove("hover:bg-blue-700")
        downloadButton.classList.add("bg-gray-700")
    }

}



function cropText(ctx,text,y)
{
    
    
    var items = trimData(text)
    ctx.fillText(items[0],32,y) 
    ctx.fillText(items[1],32,y+20) 
    ctx.fillText(items[2],32,y+40) 
    ctx.fillText(items[3],32,y+60) 



function trimData(text)
{
    var testString = text.value
    var stringArray = testString.split(" ")
    var firstPartString = ""
    var secondPartString = ""
    var thirdPartString = ""
    var fourthPartString = ""
    var firstPartArray = stringArray.slice(0,7)
    var secondPartArray = stringArray.slice(7,14)
    var thirdPartArray = stringArray.slice(14,21)
    var fourthPartArray = stringArray.slice(21,stringArray.length)
    // console.log(firstPartArray)

    for (var x=0; x<firstPartArray.length;x++)
    {
        firstPartString += firstPartArray[x] + " "
    }
    for (var j=0; j < secondPartArray.length; j++)
    {
        secondPartString += secondPartArray[j] + " "
    }
    for (var z=0; z < thirdPartArray.length; z++)
    {
        thirdPartString += thirdPartArray[z] + " "
    }
    for (var t=0; t < fourthPartArray.length; t++)
    {
        fourthPartString += fourthPartArray[t] = " "
    }
    return [firstPartString,secondPartString,thirdPartString,fourthPartString]
}

}
function getJSONdata()
{
    var name = document.getElementById("sheetArea0")
    var highConcept = document.getElementById("sheetArea1")
    var trouble = document.getElementById("sheetArea2")
    var relationship = document.getElementById("sheetArea3")
    var freeAspect1 = document.getElementById("sheetArea4")
    var freeAspect2 = document.getElementById("sheetArea5")
    var stunt1 = null
    var stunt2 = null
    var stunt3 = null
    var stunt4 = null
    var stunt5 = null
    var stunt6 = null

    if (document.getElementById("stuntArea0") != null)
    {
        stunt1 = document.getElementById("stuntArea0").value
        

    }
    if (document.getElementById("stuntArea1") != null)
    {
        stunt2 = document.getElementById("stuntArea1").value
        
        
    }   
    if (document.getElementById("stuntArea2") != null)
    {
        stunt3 = document.getElementById("stuntArea2").value
        
        
    }   
    if (document.getElementById("stuntArea3") != null)
    {
        stunt4 = document.getElementById("stuntArea3").value
        

    }   
    if (document.getElementById("stuntArea4") != null)
    {
        stunt5 = document.getElementById("stuntArea4").value
        
        
    }   
    if (document.getElementById("stuntArea5") != null)
    {
        stunt6 = document.getElementById("stuntArea5").value
        
        
    }
    var rawJson = 
    {
        "name": name.value,
        "highConcept": highConcept.value,
        "trouble": trouble.value,
        "relationship": relationship.value,
        "freeAspect1" : freeAspect1.value,
        "freeAspect2" : freeAspect2.value,
        "stunt1": stunt1,
        "stunt2": stunt2,
        "stunt3": stunt3,
        "stunt4": stunt4,
        "stunt5": stunt5,
        "stunt6": stunt6,

    }
    for (var x in dummyArray)
    {
        var skillValue = document.getElementById(x).innerHTML
        rawJson[skillArray[x]] = skillValue
    }
    var json = JSON.stringify(rawJson,undefined,4)
    console.log(json)
    const blob = new Blob([json],{type: "application/json"})
    const fileURL = URL.createObjectURL(blob)
    var downloadLink = document.createElement("a")
    downloadLink.href = fileURL
    downloadLink.download = "characterSheet.json"
    downloadLink.click();  

}

</script>

<template>
    <img src="../assets/mijasa.png" style="display:none">
    <div class = "grid justify-center text-white">
        <canvas id = "sheetCanvas" width = "946" height = "1920" class = "border-gray-600 border-x-4 border-y-4 rounded-lg my-4 bg-white">
        </canvas>
        

        
    </div>
    <div class = "flex justify-center">
        <button @click ="createSheet(0)" class = "bg-sky-800 px-2 py-2 mx-1 rounded-lg shadow-md hover:bg-sky-700">Create Sheet</button>
        <button @click ="createSheet(1)" class = "bg-red-800 px-7 py-2 mx-1 rounded-lg shadow-md hover:bg-red-700">Clear</button>
    </div>
    <div class = "flex justify-center py-5">
        <button @click="getJSONdata" id="downloadButton" class = "bg-gray-700 px-20 py-2 rounded-lg shadow-md" disabled>Download Data</button>
    </div>
</template>

