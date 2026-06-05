# project-II
Practice of javascript by making calculator 
``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="calculator.css">
</head>
<body>
        <div class="calculator">
        <input type="text" id="display" readonly>
            <button class="btn" data-value="7">7</button>
            <button class="btn" data-value="8">8</button>
            <button class="btn" data-value="9">9</button>
            <button class="btn" data-value="/">/</button>
            <button class="btn" data-value="4">4</button>
            <button class="btn" data-value="5">5</button>
            <button class="btn" data-value="6">6</button>
            <button class="btn" data-value="*">*</button>
            <button class="btn" data-value="1">1</button>
            <button class="btn" data-value="2">2</button>
            <button class="btn" data-value="3">3</button>
            <button class="btn" data-value="-">-</button>
            <button class="btn" data-value="0">0</button>
            <button class="btn" data-value=".">.</button>
            <button class="btn" id="clear">C</button>
            <button class="btn" id="backspace" data-value="⌫">⌫</button>
            <button class="btn" data-value="+">+</button>
            <button class="btn" data-value="=">=</button>
        </div>
    <script src="calculator.js"></script>
</body>
</html>

```
``` css

*{
    margin: 0;
    padding: 0;
}
html, body{
    height: 100%;
}
body{
    display: flex;
    justify-content: center;
    align-items: center;
}
.calculator{
    width: 300px;
    height: 600px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    text-align: center;
    background-color: #b7a4a4;
    box-shadow: 0 4px #999;
    border-radius: 15px;
    border: 0px solid #000;
}
#display{
    margin: 10px;
    width: 90%;
    height: 50px;
    font-size: 24px;
    text-align: right;
    padding: 10px;
    border: 0px solid #000;
    border-radius: 15px;
    background-color: #fff;
    box-shadow: 0 4px #999;
}
.btn{
    padding: 10px;
    width: 65px;
    height: 65px;
    font-size: 24px;
    margin: 10px;
    box-shadow: 0 4px #999;
    border: none;
    cursor: pointer;
    border-radius: 15px;
    background-color: #e0e0e0;
}
.btn:active{
    transform: translateY(2px);
}
```
``` js


function digits() {
    const buttons = document.querySelectorAll('.btn');
    const display = document.getElementById('display');
    buttons.forEach(button => {
        button.addEventListener('click', () => {
            const value = button.getAttribute('data-value');
            if (value === '=') {
                display.value = eval(display.value);
            }
            else if (button.id === 'clear') {
                display.value = '';
            }
            else if(button.id === 'backspace') {
                display.value = display.value.slice(0, -1);
            }
            else {
                display.value += value;
            }

        });
    });
}
digits();
``` 
