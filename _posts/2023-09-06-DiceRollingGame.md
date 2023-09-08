---
comments: true
layout: post
title: Lol
description: Grab Calculator Code and place in IPYNB
type: tangibles
courses: { compsci: {week: 3} }
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dice Rolling Game</title>
</head>
<body>
    <h1>Dice Rolling Game</h1>
    <p>Enter your bet amount: <input type="number" id="betAmount" min="1"></p>
    <button onclick="rollDice()">Roll Dice</button>
    <p>Your roll: <span id="userRoll"></span></p>
    <p>Computer's roll: <span id="computerRoll"></span></p>
    <p id="resultMessage"></p>

    <script>
        function rollDice() {
            const betAmount = parseInt(document.getElementById('betAmount').value);
            const userRoll = Math.floor(Math.random() * 6) + 1; // User's roll (1 to 6)
            const computerRoll = Math.floor(Math.random() * 6) + 1; // Computer's roll (1 to 6)

            document.getElementById('userRoll').textContent = userRoll;
            document.getElementById('computerRoll').textContent = computerRoll;

            if (computerRoll > userRoll) {
                // Computer wins
                document.getElementById('resultMessage').textContent = `You lose $${betAmount} to the computer.`;
            } else {
                // User wins or ties
                document.getElementById('resultMessage').textContent = `You win or tie!`;
            }
        }
    </script>
</body>
</html>
