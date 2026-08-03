<!DOCTYPE html>
<html>
<head>
<title>PitPlanner Shift Handover</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
body {
    font-family: Arial, sans-serif;
    background:#f2f2f2;
    padding:15px;
}

.card {
    background:white;
    padding:20px;
    border-radius:10px;
    margin-bottom:15px;
}

input, textarea, select {
    width:100%;
    padding:12px;
    margin:8px 0 15px;
    box-sizing:border-box;
    border-radius:5px;
    border:1px solid #ccc;
}

textarea {
    height:80px;
}

button {
    width:100%;
    padding:15px;
    background:#0066cc;
    color:white;
    border:0;
    border-radius:8px;
    font-size:18px;
}

.issue {
    border-left:5px solid #0066cc;
    padding-left:10px;
    margin-bottom:15px;
}
</style>

</head>

<body>

<h1>🚜 PitPlanner</h1>
<h2>Shift Handover</h2>

<div class="card">

<label>Equipment Number</label>
<input id="equipment" placeholder="Example: 793F-12">

<label>Location</label>
<input id="location" placeholder="Example: ROM">

<label>Fault Description</label>
<textarea id="fault"></textarea>

<label>Work Completed</label>
<textarea id="completed"></textarea>

<label>Outstanding Work</label>
<textarea id="outstanding"></textarea>

<label>Parts Required</label>
<textarea id="parts"></textarea>

<label>Priority</label>
<select id="priority">
<option>P1 - Critical</option>
<option>P2 - High</option>
<option>P3 - Medium</option>
<option>P4 - Low</option>
<option>P5 - Monitor</option>
</select>

<label>Completed By</label>
<input id="person">

<button onclick="saveHandover()">Save Handover</button>

</div>


<div class="card">

<h2>Previous Handovers</h2>

<div id="history"></div>

</div>


<script>

function saveHandover(){

let handover = {
equipment: equipment.value,
location: location.value,
fault: fault.value,
completed: completed.value,
outstanding: outstanding.value,
parts: parts.value,
priority: priority.value,
person: person.value,
date: new Date().toLocaleString()
};

let saved = JSON.parse(localStorage.getItem("handovers")) || [];

saved.push(handover);

localStorage.setItem("handovers", JSON.stringify(saved));

alert("Handover Saved");

displayHandovers();

}


function displayHandovers(){

let saved = JSON.parse(localStorage.getItem("handovers")) || [];

let output="";

saved.reverse().forEach(h => {

output += `
<div class="issue">
<b>${h.equipment}</b><br>
${h.priority}<br>
${h.fault}<br>
<b>Outstanding:</b> ${h.outstanding}<br>
<small>${h.date} - ${h.person}</small>
</div>
`;

});

history.innerHTML = output;

}

displayHandovers();

</script>


</body>
</html>
