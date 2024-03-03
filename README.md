# power-cosumption-calculator-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Power Consumption Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        #calculator {
            max-width: 400px;
            margin: 0 auto;
        }

        label {
            display: block;
            margin-bottom: 8px;
        }

        input {
            width: 100%;
            padding: 8px;
            margin-bottom: 16px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px;
            border: none;
            cursor: pointer;
            width: 100%;
        }

        #result {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<div id="calculator">
    <label for="numDrives">Number of Drives:</label>
    <input type="number" id="numDrives" placeholder="Enter number of drives" required>

    <label for="drivePower">Drive Power Consumption (Watts):</label>
    <input type="number" id="drivePower" placeholder="Enter drive power consumption" required>

    <label for="systemEfficiency">System Efficiency (%):</label>
    <input type="number" id="systemEfficiency" placeholder="Enter system efficiency" required>

    <button onclick="calculatePowerConsumption()">Calculate Power Consumption</button>

    <div id="result"></div>
</div>

<script>
    function calculatePowerConsumption() {
        const numDrives = parseInt(document.getElementById("numDrives").value);
        const drivePower = parseInt(document.getElementById("drivePower").value);
        const systemEfficiency = parseFloat(document.getElementById("systemEfficiency").value);

        const totalDrivePower = numDrives * drivePower;
        const totalSystemPower = totalDrivePower / (systemEfficiency / 100);

        const resultElement = document.getElementById("result");
        resultElement.innerHTML = `<p>Total Drive Power Consumption: ${totalDrivePower} Watts</p>
                                   <p>Total System Power Consumption: ${totalSystemPower.toFixed(2)} Watts</p>`;
    }
</script>

</body>
</html>
