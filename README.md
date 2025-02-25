<!DOCTYPE html>
<html>
<head>
    <title>Workers' Compensation Break-Even Calculator</title>
    <script>
        function calculate() {
            let hourlyWage = parseFloat(document.getElementById("hourlyWage").value);
            let hoursPerWeek = 40;
            let weeksPerYear = 52.14;
            let wcRateUnder32 = 9.27 / 100;
            let wcRateOver32 = 5.25 / 100;
            
            let weeklyWage = hourlyWage * hoursPerWeek;
            let annualWage = weeklyWage * weeksPerYear;
            
            let wcBurden = hourlyWage < 32 ? (annualWage * wcRateUnder32) : (annualWage * wcRateOver32);
            
            document.getElementById("weeklyWage").innerText = weeklyWage.toFixed(2);
            document.getElementById("annualWage").innerText = annualWage.toFixed(2);
            document.getElementById("wcBurden").innerText = wcBurden.toFixed(2);
        }
    </script>
</head>
<body>
    <h2>Workers' Compensation Break-Even Calculator</h2>
    <label for="hourlyWage">Hourly Wage ($):</label>
    <input type="number" id="hourlyWage" step="0.01" value="31">
    <button onclick="calculate()">Calculate</button>
    
    <h3>Results:</h3>
    <p>Weekly Wage: $<span id="weeklyWage">0.00</span></p>
    <p>Annual Wage: $<span id="annualWage">0.00</span></p>
    <p>Annual WC Burden: $<span id="wcBurden">0.00</span></p>
</body>
</html>
# wc-break-even-calculator
Hourly Wage break even point calculator for California construction companies that use split workers compensation rates
