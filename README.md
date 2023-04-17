# CodeClause_unit-converter
Internship
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <title>Unit Converter</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <h1>Unit Converter</h1>
    <div>
        <label>Enter value:</label>
        <input type="number" id="inputValue">
        <select id="inputUnit">
            <option value="meters">Meters</option>
            <option value="inches">Inches</option>
            <option value="feet">Feet</option>
        </select>
    </div>
    <div>
        <label>Convert to:</label>
        <select id="outputUnit">
            <option value="meters">Meters</option>
            <option value="inches">Inches</option>
            <option value="feet">Feet</option>
        </select>
        <button onclick="convert()">Convert</button>
    </div>
    <div>
        <label>Result:</label>
        <span id="result"></span>
    </div>
    <script src="script.js"></script>
</body>

</html>


/*CSS FILE*/

body {
  font-family: Arial, sans-serif;
  background-color: rgba(110, 104, 189, 0.442);

}

h1 {
  text-align: center;
  font-size: 50px;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;

  


}

label {
  display: inline-block;
  
  width: 700px;
  text-align: right;
  margin-right: 10px;
  margin-top: 10px;
  margin-left: auto;
  margin-right: auto;
  /* margin-bottom: 10px; */
   
 
}

input[type=number] {
  width: 100px;
  padding: 15px;
  margin-right: 20px;
  
}

select {
  width: 100px;
  padding: 15px;
  margin-right: 20px;
}

button {
  padding: 5px;
  border-radius: 15px;
  background-color: rgb(227, 91, 91);
}

#result {
  font-weight: bold;
}


/* javascript file*/
function convert() {
  const inputValue = document.getElementById("inputValue").value;
  const inputUnit = document.getElementById("inputUnit").value;
  const outputUnit = document.getElementById("outputUnit").value;
  let result;

  if (inputUnit === "meters") {
    if (outputUnit === "inches") {
      result = inputValue * 39.37;
    } else if (outputUnit === "feet") {
      result = inputValue * 3.281;
    } else {
      result = inputValue;
    }
  } else if (inputUnit === "inches") {
    if (outputUnit === "meters") {
      result = inputValue / 39.37;
    } else if (outputUnit === "feet") {
      result = inputValue / 12;
    } else {
      result = inputValue;
    }
  } else {
    if (outputUnit === "meters") {
      result = inputValue / 3.281;
    } else if (outputUnit === "inches") {
      result = inputValue * 12;
    } else {
      result = inputValue;
    }
  }

  document.getElementById("result").textContent = result.toFixed(2) + " " + outputUnit;
}
