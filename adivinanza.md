<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Adivina el número</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
  </style>
</head>
<body>
  <h1>Adivina el número (entre 1 y 100)</h1>
  <input type="text" id="guessField">
  <button onclick="checkGuess()">Adivinar</button>
  <p id="message"></p>

  <script>
    // Generar un número aleatorio entre 1 y 100
    const randomNumber = Math.floor(Math.random() * 100) + 1;
    console.log(randomNumber);

    const guessField = document.getElementById('guessField');
    const message = document.getElementById('message');

    let guesses = 0;

    function checkGuess() {
      let userGuess = parseInt(guessField.value);
      guesses++;

      if (userGuess === randomNumber) {
        message.textContent = `¡Felicidades! Adivinaste el número en ${guesses} intentos.`;
        message.style.backgroundColor = 'green';
        endGame();
      } else if (userGuess > randomNumber) {
        message.textContent = 'El número es menor.';
        message.style.backgroundColor = 'red';
      } else {
        message.textContent = 'El número es mayor.';
        message.style.backgroundColor = 'red';
      }
    }

    function endGame() {
      guessField.disabled = true;
      guessField.style.backgroundColor = 'lightgrey';
    }
  </script>
</body>
</html>
