---
comments: true
layout: post
title: Hangman Game
description: Table made by us to make tables
type: hacks
courses: { compsci: {week: 3} }
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Hangman Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #word-display {
            font-size: 24px;
            margin-bottom: 10px;
        }
        #hangman {
            font-size: 24px;
        }
    </style>
</head>
<body>
    <h1>Hangman Game</h1>
    <div id="word-display"></div>
    <div id="hangman">O</div>
    <div>
        <label for="guess">Guess a letter: </label>
        <input type="text" id="guess" maxlength="1">
        <button onclick="checkGuess()">Submit</button>
    </div>
    <div id="message"></div>
    <script>
        const words = ['apple', 'banana', 'cherry', 'date', 'elderberry', 'fig', 'grape', 'honeydew', 'kiwi', 'lemon', 'mango', 'nectarine', 'orange', 'papaya', 'quince'];
        const maxAttempts = 6;
        let chosenWord;
        let displayedWord;
        let attemptsLeft;
        let guessedLetters = [];
        function startGame() {
            chosenWord = words[Math.floor(Math.random() * words.length)];
            displayedWord = '_'.repeat(chosenWord.length);
            attemptsLeft = maxAttempts;
            guessedLetters = [];
            updateDisplay();
        }
        function updateDisplay() {
            document.getElementById('word-display').textContent = displayedWord;
            document.getElementById('hangman').textContent = 'Attempts Left: ' + attemptsLeft;
            document.getElementById('message').textContent = guessedLetters.join(', ');
            if (displayedWord === chosenWord) {
                document.getElementById('message').textContent = 'You win!';
            } else if (attemptsLeft === 0) {
                document.getElementById('message').textContent = 'You lose! The word was ' + chosenWord;
            }
        }
        function checkGuess() {
            const guess = document.getElementById('guess').value.toLowerCase();
            if (!guess.match(/[a-z]/)) {
                alert('Please enter a valid letter.');
                return;
            }
            if (guessedLetters.includes(guess)) {
                alert('You already guessed that letter.');
                return;
            }
            guessedLetters.push(guess);
            if (chosenWord.includes(guess)) {
                for (let i = 0; i < chosenWord.length; i++) {
                    if (chosenWord[i] === guess) {
                        displayedWord = displayedWord.substr(0, i) + guess + displayedWord.substr(i + 1);
                    }
                }
            } else {
                attemptsLeft--;
            }
            updateDisplay();
        }
        startGame();
    </script>
</body>
</html>
