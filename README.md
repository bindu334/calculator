<!DOCTYPE html>
<html>
<head>
    <title>
          Scientific Calculator using HTML, CSS and Js
      </title><script src=
      "https://cdnjs.cloudflare.com/ajax/libs/mathjs/10.6.4/math.js"
                  integrity=
      "sha512-BbVEDjbqdN3Eow8+empLMrJlxXRj5nEitiCAK5A1pUr66+jLVejo3PmjIaucRnjlB0P9R3rBUs3g5jXc8ti+fQ=="
                  crossorigin="anonymous"
                  referrerpolicy="no-referrer">
            </script>
      <link rel="stylesheet" href="scientific.css"> 
</head>
 
<body>
    <h1 style="color: green; text-align: center;">
        Scientific Calculator</h1>
    <form>
        <table>
            <tr>
                <td colspan="6">
                    <input id="display" type="text">
                </td>
            </tr>
            <tr>
                <td><input type="button" value="1"
                           onclick="display.value += '1'"></td>
                <td><input type="button" value="2"
                           onclick="display.value += '2'"></td>
                <td><input type="button" value="3"
                           onclick="display.value += '3'"></td>
                <td><input type="button" value="C"
                           onclick="display.value = ''"></td>
                <td><input type="button" value="⌫"
                           onclick="backspace()"></td>
                <td><input type="button" value="="
                           onclick="calculate()"></td>
            </tr>
            <tr>
                <td><input type="button" value="4"
                           onclick="display.value += '4'"></td>
                <td><input type="button" value="5"
                           onclick="display.value += '5'"></td>
                <td><input type="button" value="6"
                           onclick="display.value += '6'"></td>
                <td><input type="button" value="-"
                           onclick="display.value += '-'"></td>
                <td><input type="button" value="%"
                           onclick="display.value += '%'"></td>
                <td><input type="button" value="cos("
                           onclick="display.value += 'cos('"></td>
            </tr>
            <tr>
                <td><input type="button" value="7"
                           onclick="display.value += '7'"></td>
                <td><input type="button" value="8"
                           onclick="display.value += '8'"></td>
                <td><input type="button" value="9"
                           onclick="display.value += '9'"></td>
                <td><input type="button" value="x"
                           onclick="display.value += '*'"></td>
                <td><input type="button" value="!"
                           onclick="display.value += '!'"></td>
                <td><input type="button" value="sin("
                           onclick="display.value += 'sin('"></td>
            </tr>
            <tr>
                <td><input type="button" value="."
                           onclick="display.value += '.'"></td>
                <td><input type="button" value="0"
                           onclick="display.value += '0'"></td>
                <td><input type="button" value=","
                           onclick="display.value += ','"></td>
                <td><input type="button" value="+"
                           onclick="display.value += '+'"></td>
                <td><input type="button" value="/"
                           onclick="display.value += '/'"></td>
                <td><input type="button" value="tan("
                           onclick="display.value += 'tan('"></td>
            </tr>
            <tr>
                <td><input type="button" value="E"
                           onclick="e()"></td>
                <td><input type="button" value="pi"
                           onclick="pi()"></td>
                <td><input type="button" value="^"
                           onclick="power()"></td>
                <td><input type="button" value="("
                           onclick="display.value += '('"></td>
                <td><input type="button" value=")"
                           onclick="display.value += ')'"></td>
                <td><input type="button" value="log("
                           onclick="base10Log()"></td>
            </tr>
            <tr>
                <td><input type="button" value="sqrt("
                           onclick="squareRoot()"></td>
                <td><input type="button" value="ln2"
                           onclick="display.value += Math.LN2"></td>
                <td><input type="button" value="log10("
                           onclick="base10Log()"></td>
                <td><input type="button" value="l2e"
                           onclick="display.value += Math.LOG2E"></td>
                <td><input type="button" value="l10e"
                           onclick="display.value += Math.LOG10E"></td>
                <td><input type="button" value="exp("
                           onclick="display.value += 'exp('"></td>
            </tr>
        </table>
    </form>
    <script type="text/javascript" src="scientific.js"></script>
</body>
</html>










table {
    border: 1px solid black;
    margin-left: auto;
    margin-right: auto;
}
 
input[type="button"] {
    width: 100%;
    padding: 20px 40px;
    background-color: green;
    color: white;
    font-size: 24px;
    font-weight: bold;
    border: none;
    border-radius: 5px;
}
 
input[type="text"] {
    padding: 20px 240px;
    font-size: 24px;
    font-weight: bold;
    border: none;
    border-radius: 5px;
    border: 2px solid black;
    text-align: left;
}
 
display {
    text-align: left;
}





















function backspace() {
    let display = document.getElementById("display");
    display.value = display.value.slice(0, -1);
}

function calculate() {
    let display = document.getElementById("display");
    let expression = display.value;
    let result;

    try {
        // Convert trigonometric function inputs from degrees to radians
        expression = expression.replace(/sin\(/g, 'sin(' + Math.PI / 180 + '*');
        expression = expression.replace(/cos\(/g, 'cos(' + Math.PI / 180 + '*');
        expression = expression.replace(/tan\(/g, 'tan(' + Math.PI / 180 + '*');

        result = math.evaluate(expression);
        display.value = result;
    } catch (error) {
        display.value = "Error";
    }
}

function squareRoot() {
    let display = document.getElementById("display");
    display.value += "sqrt(";
}

function base10Log() {
    let display = document.getElementById("display");
    display.value += "log(";
}

function pi() {
    let display = document.getElementById("display");
    display.value += "pi";
}

function e() {
    let display = document.getElementById("display");
    display.value += "e";
}

function power() {
    let display = document.getElementById("display");
    display.value += "^(";
}









