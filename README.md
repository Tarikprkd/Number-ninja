# Number-ninja
a thrilling guessing game! Your goal is to guess a randomly selected number between 1 and 100. Input your guess and click "Guess!" to receive feedback. Is it too low, too high, or correct? Track your attempts and challenge yourself to guess the number in the fewest tries. Ready for the quest? Let the fun begin!
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number Guessing Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            text-align: center;
            padding: 50px;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            display: inline-block;
        }
        input {
            padding: 10px;
            margin: 10px 0;
            width: 70px;
        }
        button {
            padding: 10px 20px;
            background-color: #333;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #555;
        }
        p {
            font-size: 1.2em;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Number Guessing Game</h1>
        <p>Guess a number between 1 and 100:</p>
        <input type="number" id="guess" min="1" max="100">
        <button onclick="checkGuess()">Guess!</button>
        <p id="result"></p>
        <p id="attempts"></p>
    </div>

    <script>
        const randomNumber = Math.floor(Math.random() * 100) + 1;
        let attempts = 0;

        function checkGuess() {
            const userGuess = Number(document.getElementById('guess').value);
            const resultText = document.getElementById('result');
            const attemptsText = document.getElementById('attempts');
            attempts++;

            if (userGuess === randomNumber) {
                resultText.textContent = `Correct! You guessed the number in ${attempts} attempts.`;
                attemptsText.textContent = '';
            } else if (userGuess < 1 || userGuess > 100) {
                resultText.textContent = "Please choose a number between 1 and 100.";
                attemptsText.textContent = '';
            } else if (userGuess < randomNumber) {
                resultText.textContent = "Too low! Try again.";
                attemptsText.textContent = `Attempts: ${attempts}`;
            } else {
                resultText.textContent = "Too high! Try again.";
                attemptsText.textContent = `Attempts: ${attempts}`;
            }
        }
    </script>
</body>
</html>
