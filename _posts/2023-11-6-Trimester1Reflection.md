---
comments: true
layout: post
title: End of Tri Reflection
description: Ticket
type: tangibles
courses: { compsci: {week: 11} }
---
<html>
<head>
    <title>Trimester Reflection</title>
</head>
<body>
    <h1>Trimester Reflection</h1>
    <p>
        The past trimester has been a pivotal period in my academic journey, marked by significant growth and profound learning experiences. In my exploration of basic Python programming, I encountered the foundational principles that underpin the world of coding. From understanding variables, data types, and control structures to delving into functions, loops, and conditional statements, I grasped the essential building blocks of programming. These concepts laid the groundwork for more advanced coding adventures.
    </p>
    <p>
        One of the highlights of this trimester was my foray into version control systems, particularly GitHub. Learning how to use Git and GitHub to manage and collaborate on coding projects was a game-changer. I discovered the power of version control, enabling me to track changes, collaborate seamlessly with peers, and contribute to open-source projects. GitHub's platform proved to be an invaluable tool for code hosting and project management.
    </p>
    <p>
        As I ventured deeper into the realm of coding, I tackled complex problems and projects, honing my problem-solving and debugging skills. I also had the privilege of working on group coding assignments, which fostered teamwork, communication, and the exchange of diverse perspectives. These experiences enriched my coding abilities and expanded my horizons.
    </p>
    <p>
        Looking forward to the next trimester, I am excited about building on this foundation. I intend to explore more advanced coding concepts and take on increasingly complex coding challenges. I will continue to deepen my understanding of version control systems, leveraging tools like Git and GitHub to enhance collaboration and streamline project management. This trimester has equipped me with essential skills and knowledge, and I am confident that I am well-prepared for the exciting coding adventures that lie ahead.
    </p>
</body>
</html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Sports Betting Simulator</title>
</head>
<body>
    <h1>Sports Betting Simulator</h1>
    <label for="player-search">Search for a Player: </label>
    <input type="text" id="player-search">
    <button onclick="searchPlayer()">Search</button>
    <div id="player-description"></div>
    <h2>Place a Bet</h2>
    <label for="bet-player">Select a Player: </label>
    <select id="bet-player">
        <option value="Cooper Kupp NFL">Cooper Kupp NFL</option>
        <option value="Lamar Jackson NFL">Lamar Jackson NFL</option>
        <option value="Patrick Mahomes NFL">Patrick Mahomes NFL</option>
        <option value="Tyreek Hill NFL">Tyreek Hill NFL</option>
        <option value="Josh Allen NFL">Josh Allen NFL</option>
    </select>
    <label for="bet-amount">Bet Amount: $</label>
    <input type="number" id="bet-amount">
    <button onclick="placeBet()">Bet</button>
    <div id="bet-result"></div>
    <script>
        const playerData = [
            {
                name: "Cooper Kupp NFL",
                description: "Cooper Kupp is a talented wide receiver in the NFL known for his precise route running and sure hands. He has been a consistent performer, making him a reliable pick for fantasy football enthusiasts.",
                isGoodPick: true,
                winPercentage: 10.5,
                additionalInfo: "Cooper Kupp has been in excellent form recently, making him a solid bet. However, he is sadly on injury reserve. Even though he would have been one of the best players this season he sadly can live up to it and when he comes back its likely that it wont be much better."
            },
            {
                name: "Lamar Jackson NFL",
                description: "Lamar Jackson is a dynamic quarterback in the NFL. His dual-threat abilities make him an exciting player to watch. When he's on form, he can be an excellent pick for fantasy football.",
                isGoodPick: true,
                winPercentage: 60.6,
                additionalInfo: "Lamar Jackson's recent performance suggests a good chance of success in this bet. He is vestaile and has cemented the idea of him being a legend throughout history of the NFL. If I had to bet my money on someone he would be a good option but as of right now, there are many different picks that are seen as better."
            },
            {
                name: "Patrick Mahomes NFL",
                description: "Patrick Mahomes is one of the most electrifying quarterbacks in the NFL. His ability to throw accurately on the run and his deep-passing skills make him a top choice for fantasy football.",
                isGoodPick: true,
                winPercentage: 90.2,
                additionalInfo: "Patrick Mahomes has a high win percentage, making him a strong bet. He is know for being one of the best quarterbacks of all time. He singlehandly brought his team up in the ranks with his impressive skills. he is one of my personal favorite players and has made a great name for himself and betting on him is high chance of sucess."
            },
            {
                name: "Tyreek Hill NFL",
                description: "Tyreek Hill, also known as 'Cheetah,' is a speedy wide receiver who can turn any play into a touchdown. He is a fantasy football favorite due to his big-play potential.",
                isGoodPick: true,
                winPercentage: 82.34,
                additionalInfo: "Tyreek Hill's exceptional speed gives him an edge, making this bet a good choice. One of the best wide recievers in NFL history. He is one of the most explosive players and having him on your team could mean the difference. His seasons have always been consistent but lets see how he performs this season and I am exicted to see him grow."
            },
            {
                name: "Josh Allen NFL",
                description: "Josh Allen is a strong-armed quarterback with a penchant for scoring touchdowns, both through the air and on the ground. He is a valuable pick in fantasy football leagues.",
                isGoodPick: true,
                winPercentage: 74.3,
                additionalInfo: "Josh Allen's versatility makes him a strong candidate for a successful bet. Josh Allen is another great quarterback with a bunch of potential this season. He can definetly bring his team up and make it so that it can change the NFL. Exicted to see what will happen this upcomming season."
            }
        ];
        function searchPlayer() {
            const playerName = document.getElementById('player-search').value;
            const playerDescription = document.getElementById('player-description');
            const player = playerData.find(p => p.name.toLowerCase() === playerName.toLowerCase());
            if (player) {
                const description = player.description;
                const isGoodPick = player.isGoodPick ? "a good pick" : "not a good pick";
                const winPercentage = player.winPercentage;
                const additionalInfo = player.additionalInfo;
                const result = `<p>${description}</p><p>This player is considered ${isGoodPick} for fantasy football.</p><p>Win Percentage: ${winPercentage}%</p><p>${additionalInfo}</p>`;
                playerDescription.innerHTML = result;
            } else {
                playerDescription.innerHTML = '<p>Player not found.</p>';
            }
        }
        function placeBet() {
            const selectedPlayer = document.getElementById('bet-player').value;
            const betAmount = parseFloat(document.getElementById('bet-amount').value);
            const player = playerData.find(p => p.name === selectedPlayer);
            if (player) {
                const winPercentage = player.winPercentage;
                const isGoodPick = winPercentage >= 70;
                const result = isGoodPick
                    ? `You placed a $${betAmount} bet on ${selectedPlayer}. The win percentage is ${winPercentage}%, which suggests it's a good pick.`
                    : `You placed a $${betAmount} bet on ${selectedPlayer}. The win percentage is ${winPercentage}%, which suggests it's not a good pick.`;
                document.getElementById('bet-result').textContent = result;
            } else {
                document.getElementById('bet-result').textContent = 'Player not found.';
            }
        }
    </script>
</body>
</html>

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
