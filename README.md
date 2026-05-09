<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculadora</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #5f5f61;
      font-family: Arial, sans-serif;
      margin: 0;
    }
    .calculadora {
      background: #2a2a3c;
      padding: 20px;
      border-radius: 16px;
      box-shadow: 0 8px 24px rgba(0,0,0,0.4);
      width: 320px;
    }
    #display {
      width: 100%;
      height: 60px;
      margin-bottom: 16px;
      background: #1e1e2e;
      color: #cdd6f4;
      font-size: 2rem;
      text-align: right;
      padding: 10px;
      border: none;
      border-radius: 8px;
      box-sizing: border-box;
    }
    .botoes {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      height: 60px;
      font-size: 1.2rem;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: #45475a;
      color: #cdd6f4;
      transition: 0.2s;
    }
    button:hover {
      background: #585b70;
    }
    .operador {
      background: #f38ba8;
      color: #1e1e2e;
    }
    .operador:hover {
      background: #f5a3b8;
    }
    .igual {
      background: #a6e3a1;
      color: #1e1e2e;
      grid-column: span 2;
    }
    .igual:hover {
      background: #b7e8b2;
    }
    .limpar {
      background: #fab387;
      color: #1e1e2e;
    }
  </style>
</head>
<body>
  <div class="calculadora">
    <input type="text" id="display" disabled>
    <div class="botoes">
      <button class="limpar" onclick="limpar()">C</button>
      <button onclick="addChar('/')">/</button>
      <button onclick="addChar('*')">*</button>
      <button class="operador" onclick="apagar()">⌫</button>
      
      <button onclick="addChar('7')">7</button>
      <button onclick="addChar('8')">8</button>
      <button onclick="addChar('9')">9</button>
      <button class="operador" onclick="addChar('-')">-</button>
      
      <button onclick="addChar('4')">4</button>
      <button onclick="addChar('5')">5</button>
      <button onclick="addChar('6')">6</button>
      <button class="operador" onclick="addChar('+')">+</button>
      
      <button onclick="addChar('1')">1</button>
      <button onclick="addChar('2')">2</button>
      <button onclick="addChar('3')">3</button>
      <button onclick="raiz()">√</button>
      
      <button onclick="addChar('0')">0</button>
      <button onclick="addChar('.')">.</button>
      <button class="igual" onclick="calcular()">=</button>
    </div>
  </div>

  <script>
    let display = document.getElementById('display');
    
    function addChar(char) {
      display.value += char;
    }
    
    function limpar() {
      display.value = '';
    }
    
    function apagar() {
      display.value = display.value.slice(0, -1);
    }
    
    function raiz() {
      try {
        display.value = Math.sqrt(eval(display.value));
      } catch {
        display.value = 'Erro';
      }
    }
    
    function calcular() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = 'Erro';
      }
    }
  </script>
</body>
</html>
