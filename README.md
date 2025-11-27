# -OIBSIP
Web development and design
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simple Calculator</title>

<style>
    body {
        background: #e8ecf1;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        font-family: Arial, sans-serif;
    }

    .calculator {
        background: #1e1e1e;
        padding: 20px;
        border-radius: 15px;
        width: 320px;
        box-shadow: 0 4px 10px rgba(0,0,0,0.4);
    }

    .display {
        width: 100%;
        height: 60px;
        background: #000;
        color: #0f0;
        font-size: 28px;
        text-align: right;
        padding: 10px;
        border-radius: 10px;
        margin-bottom: 15px;
        box-sizing: border-box;
    }

    .buttons {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 10px;
    }

    button {
        padding: 18px;
        font-size: 20px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        background: #333;
        color: #fff;
        transition: 0.2s;
    }

    button:hover {
        background: #444;
    }

    .operator {
        background: #ff9500;
    }

    .operator:hover {
        background: #e08900;
    }

    .equal {
        background: #28a745;
        grid-column: span 2;
    }

    .equal:hover {
        background: #218838;
    }

    .clear {
        background: #dc3545;
    }

    .clear:hover {
        background: #b52a37;
    }

</style>
</head>
<body>

<div class="calculator">
    <div id="display" class="display"></div>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="deleteLast()">⌫</button>
        <button class="operator" onclick="appendValue('/')">÷</button>
        <button class="operator" onclick="appendValue('*')">×</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button class="operator" onclick="appendValue('-')">−</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button class="operator" onclick="appendValue('+')">+</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button class="equal" onclick="calculate()">=</button>

        <button onclick="appendValue('0')" style="grid-column: span 2;">0</button>
        <button onclick="appendValue('.')">.</button>
    </div>
</div>

<script>
    let display = document.getElementById("display");

    function appendValue(value) {
        display.innerHTML += value;
    }

    function clearDisplay() {
        display.innerHTML = "";
    }

    function deleteLast() {
        display.innerHTML = display.innerHTML.slice(0, -1);
    }

    function calculate() {
        try {
            display.innerHTML = eval(display.innerHTML);
        } catch {
            display.innerHTML = "Error";
        }
    }
</script>

</body>
</html>
