<!DOCTYPE html>
<html>
<head>
	<title>Table Generator</title>
	<style>
		table, th, td {
			border: 1px solid black;
			border-collapse: collapse;
		}
	</style>
</head>
<body>
	<h2>Table Generator</h2>
	<form id="tableForm">
		<label for="rows">Number of Rows:</label>
		<input type="number" id="rows" name="rows" min="1" max="10"><br><br>
		<label for="cols">Number of Columns:</label>
		<input type="number" id="cols" name="cols" min="1" max="10"><br><br>
		<button type="button" onclick="generateTable()">Generate Table</button>
	</form>
	<br>
	<div id="tableContainer"></div>

	<script>
		function generateTable() {
			
			var rows = document.getElementById("rows").value;
			var cols = document.getElementById("cols").value;

			
			var table = document.createElement("table");

			
			for (var i = 0; i < rows; i++) {
				var row = document.createElement("tr");
				for (var j = 0; j < cols; j++) {
					var cell = document.createEl
					
					var content = prompt("Enter content for cell (" + (i+1) + "," + (j+1) + "):");

					cell.innerText = content ? content : "";

					row.appendChild(cell);
				}
				table.appendChild(row);
			}

			
			var tableContainer = document.getElementById("tableContainer");
			tableContainer.appendChild(table);
		}

		var form = document.getElementById("tableForm");
		form.addEventListener("submit", function(event) {
			event.preventDefault(); 
			generateTable(); 
		});
	</script>
</body>
</html>
