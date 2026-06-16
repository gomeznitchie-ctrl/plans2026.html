<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Plans 2026</title>

<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap" rel="stylesheet">

<style>

body{
    margin:0;
    background:white;
    font-family:Arial,sans-serif;
    color:#b49b6b;
}

header{
    text-align:center;
    padding:25px 15px;
}

h1{
    font-family:'Dancing Script',cursive;
    font-size:52px;
    margin:0;
}

.subtitle{
    margin-top:8px;
    font-size:16px;
}

.container{
    max-width:700px;
    margin:auto;
    padding:15px;
}

.tabs{
    display:flex;
    flex-wrap:wrap;
    gap:8px;
    justify-content:center;
    margin-bottom:15px;
}

.tab-btn{
    border:none;
    border-radius:20px;
    padding:10px 14px;
    background:#efe5cf;
    color:#8c7750;
    cursor:pointer;
    font-size:14px;
}

.tab-content{
    display:none;
    background:#fafafa;
    border-radius:15px;
    padding:15px;
    box-shadow:0 0 10px rgba(0,0,0,0.05);
}

.active{
    display:block;
}

textarea{
    width:100%;
    min-height:250px;
    border:1px solid #ddd;
    border-radius:12px;
    padding:12px;
    box-sizing:border-box;
    font-size:14px;
}

.buttons{
    margin-top:12px;
    display:flex;
    gap:10px;
}

.action{
    border:none;
    border-radius:10px;
    padding:10px 15px;
    cursor:pointer;
    font-size:16px;
}

.save{
    background:#d8c19b;
}

.discard{
    background:#f0e8db;
}

</style>
</head>

<body>

<header>
<h1>Closing the Distance</h1>
<h1> Plans 2026</h1>
<div class="subtitle">
🇨🇭Nico and 🇵🇭 Chi
</div>
</header>

<div class="container">

<div class="tabs">

<button class="tab-btn" onclick="openTab('engagement')">Engagement</button>

<button class="tab-btn" onclick="openTab('marriage')">Marriage</button>

<button class="tab-btn" onclick="openTab('visaProcess')">Visa Process</button>

<button class="tab-btn" onclick="openTab('language')">Language Requirements</button>

<button class="tab-btn" onclick="openTab('visaReq')">Visa Requirements</button>

<button class="tab-btn" onclick="openTab('ideas')">Ideas & Links</button>

</div>

<div id="engagement" class="tab-content active">

<h3>Step-by-Step Process</h3>

<textarea id="engagementText">
1. Discuss engagement timeline.
2. Decide where engagement will take place.
3. Meet families if possible.
4. Set target marriage date.
5. Create wedding budget.
6. Add your own notes below.
</textarea>

<div class="buttons">
<button class="action save" onclick="saveData('engagementText')">✔ Save</button>
<button class="action discard" onclick="discardData('engagementText')">❌ Discard</button>
</div>

</div>

<div id="marriage" class="tab-content">

<h3>Step-by-Step Process</h3>

<textarea id="marriageText">
1. Decide marriage location.
2. Gather civil documents.
3. Prepare translations if needed.
4. Schedule marriage appointment.
5. Register marriage.
6. Add your own notes below.
</textarea>

<div class="buttons">
<button class="action save" onclick="saveData('marriageText')">✔ Save</button>
<button class="action discard" onclick="discardData('marriageText')">❌ Discard</button>
</div>

</div>

<div id="visaProcess" class="tab-content">

<h3>Step-by-Step Process</h3>

<textarea id="visaProcessText">
1. Complete marriage registration.
2. Collect spouse visa requirements.
3. Submit application.
4. Wait for canton approval.
5. Receive visa decision.
6. Prepare move to Switzerland.
</textarea>

<div class="buttons">
<button class="action save" onclick="saveData('visaProcessText')">✔ Save</button>
<button class="action discard" onclick="discardData('visaProcessText')">❌ Discard</button>
</div>

</div>

<div id="language" class="tab-content">

<h3>Language Requirements</h3>

<textarea id="languageText">
Possible preparation:

• German A1
• German A2
• German B1

Add schools, schedules and notes here.
</textarea>

<div class="buttons">
<button class="action save" onclick="saveData('languageText')">✔ Save</button>
<button class="action discard" onclick="discardData('languageText')">❌ Discard</button>
</div>

</div>

<div id="visaReq" class="tab-content">

<h3>Visa Requirements</h3>

<textarea id="visaReqText">
Examples:

• Passport
• Marriage Certificate
• Visa Forms
• Photos
• Financial Documents
• Language Documents (if required)

Add more requirements here.
</textarea>

<div class="buttons">
<button class="action save" onclick="saveData('visaReqText')">✔ Save</button>
<button class="action discard" onclick="discardData('visaReqText')">❌ Discard</button>
</div>

</div>

<div id="ideas" class="tab-content">

<h3>Ideas & Links</h3>

<textarea id="ideasText">
Paste wedding ideas, embassy links, budgets, hotels, flights, inspirations and notes here.
</textarea>

<div class="buttons">
<button class="action save" onclick="saveData('ideasText')">✔ Save</button>
<button class="action discard" onclick="discardData('ideasText')">❌ Discard</button>
</div>

</div>

</div>

<script>

function openTab(id){

document.querySelectorAll('.tab-content').forEach(tab=>{
tab.classList.remove('active');
});

document.getElementById(id).classList.add('active');
}

function saveData(id){

localStorage.setItem(
id,
document.getElementById(id).value
);

alert("Saved!");
}

function discardData(id){

document.getElementById(id).value='';
localStorage.removeItem(id);

alert("Discarded!");
}

window.onload=function(){

[
'engagementText',
'marriageText',
'visaProcessText',
'languageText',
'visaReqText',
'ideasText'
]

.forEach(id=>{

let saved=localStorage.getItem(id);

if(saved){
document.getElementById(id).value=saved;
}

});

};

</script>

</body>
</html>
