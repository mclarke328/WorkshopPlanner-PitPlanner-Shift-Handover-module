index.html
<!DOCTYPE html>
<html>
<head>
    <title>PitPlanner Shift Handover</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f2f2f2;
            padding: 15px;
        }

        h1 {
            text-align: center;
        }

        .card {
            background: white;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 15px;
        }

        input, textarea, select {
            width: 100%;
            padding: 12px;
            margin-top: 8px;
            margin-bottom: 15px;
            border-radius: 5px;
            border: 1px solid #ccc;
            box-sizing: border-box;
        }

        textarea {
            height: 100px;
        }

        button {
            width: 100%;
            padding: 15px;
            background: #0066cc;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 18px;
        }

        .priority {
            font-weight: bold;
        }
    </style>
</head>

<body>

<h1>🚜 PitPlanner</h1>
<h2>Shift Handover</h2>

<div class="card">

<label>Equipment Number</label>
<input type="text" placeholder="Example: 793F-12">

<label>Location</label>
<input type="text" placeholder="Example: ROM / Workshop">

<label>Fault Description</label>
<textarea placeholder="Describe the issue..."></textarea>

<label>Work Completed</label>
<textarea placeholder="What has been done?"></textarea>

<label>Outstanding Work</label>
<textarea placeholder="What still needs to happen?"></textarea>

<label>Parts Required</label>
<textarea placeholder="Parts, materials or support required"></textarea>

<label class="priority">Priority</label>
<select>
    <option>Priority 1 - Critical</option>
    <option>Priority 2 - High</option>
    <option>Priority 3 - Medium</option>
    <option>Priority 4 - Low</option>
    <option>Priority 5 - Monitor</option>
</select>

<label>Completed By</label>
<input type="text" placeholder="Name">

<button>
Submit Handover
</button>

</div>

<div class="card">
<h3>Current Issues</h3>

<p>🔴 793F-12 Steering Fault</p>
<p>🟠 Drill 04 Hydraulic Leak</p>

</div>

</body>
</html>
