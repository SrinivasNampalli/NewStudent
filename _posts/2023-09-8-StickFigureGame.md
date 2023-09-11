---
comments: true
layout: post
title: StickFigure Game
description: Grab Calculator Code and place in IPYNB
type: hacks
courses: { compsci: {week: 3} }
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Obstacle Game with Timer</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
        }
        #game-container {
            width: 400px;
            height: 400px;
            margin: 0 auto;
            border: 1px solid #000;
            position: relative;
            display: none;
        }
        #player {
            width: 50px;
            height: 50px;
            background-color: blue;
            position: absolute;
            bottom: 0;
        }
        .obstacle {
            width: 20px;
            height: 20px;
            position: absolute;
        }
        .circle {
            background-color: red;
            border-radius: 50%;
        }
        .square {
            background-color: green;
        }
        .triangle {
            width: 0;
            height: 0;
            border-left: 10px solid transparent;
            border-right: 10px solid transparent;
            border-bottom: 20px solid yellow;
        }
        #timer {
            position: absolute;
            top: 10px;
            right: 10px;
        }
        #menu-container {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .start-button {
            padding: 10px 20px;
            background-color: #00f;
            color: #fff;
            font-size: 18px;
            cursor: pointer;
        }
        .level-button {
            padding: 10px 20px;
            background-color: #00f;
            color: #fff;
            font-size: 18px;
            cursor: pointer;
            display: none;
        }
    </style>
</head>
<body>
    <div id="menu-container">
        <div class="start-button" onclick="startGame()">Start</div>
        <div id="level-select-message" style="display: none;">Select a level:</div>
        <div class="level-button" onclick="startLevel(1)" style="display: none;">Level 1</div>
        <div class="level-button" onclick="startLevel(2)" style="display: none;">Level 2</div>
        <div class="level-button" onclick="startLevel(3)" style="display: none;">Level 3</div>
    </div>
    <div id="game-container">
        <div id="player"></div>
    </div>
    <div id="timer">Time: 0s</div>
    <script>
        const gameContainer = document.getElementById('game-container');
        const player = document.getElementById('player');
        const timerElement = document.getElementById('timer');
        const menuContainer = document.getElementById('menu-container');
        const startButton = document.querySelector('.start-button');
        const levelButtons = document.querySelectorAll('.level-button');
        const levelSelectMessage = document.getElementById('level-select-message');
        let playerPosition = 0;
        let startTime = null;
        let endTime = null;
        let selectedLevel = null;
        let timerInterval;
        let animationFrameId;
        // Function to move the player left or right
        function movePlayer(direction) {
            if (direction === 'left' && playerPosition > 0) {
                playerPosition -= 5; // Adjust the player movement speed
            } else if (direction === 'right' && playerPosition < 350) {
                playerPosition += 5; // Adjust the player movement speed
            }
            player.style.left = playerPosition + 'px';
        }
        // Event listener for keydown events to control player movement
        document.addEventListener('keydown', function (event) {
            if (event.key === 'ArrowLeft') {
                movePlayer('left');
            } else if (event.key === 'ArrowRight') {
                movePlayer('right');
            }
        });
        // Function to start the game
        function startGame() {
            startButton.style.display = 'none';
            levelSelectMessage.style.display = 'block';
            levelButtons.forEach(button => {
                button.style.display = 'block';
            });
        }
        // Function to start a level
        function startLevel(level) {
            selectedLevel = level;
            menuContainer.style.display = 'none';
            gameContainer.style.display = 'block';
            playerPosition = 0;
            player.style.left = playerPosition + 'px';
            timerElement.textContent = 'Time: 0s';
            startTime = new Date().getTime();
            levelButtons.forEach(button => {
                button.style.display = 'none';
            });
            timerInterval = setInterval(function () {
                const currentTime = new Date().getTime();
                const elapsedTime = (currentTime - startTime) / 1000;
                timerElement.textContent = 'Time: ' + elapsedTime.toFixed(2) + 's';
            }, 10);
            // Start spawning obstacles
            spawnObstacles(selectedLevel);
            // Start player movement animation
            movePlayer('right');
        }
        // Function to spawn obstacles
        function spawnObstacles(level) {
            let obstacleCount = 0;
            switch (level) {
                case 1:
                    obstacleCount = 8; // Increase the number of obstacles for level 1
                    break;
                case 2:
                    obstacleCount = 12; // Increase the number of obstacles for level 2
                    break;
                case 3:
                    obstacleCount = 16; // Increase the number of obstacles for level 3
                    break;
                default:
                    obstacleCount = 8; // Default to 8 obstacles
            }
            function createObstacle() {
                if (obstacleCount > 0) {
                    const obstacle = document.createElement('div');
                    obstacle.className = 'obstacle';
                    // Randomly choose a shape
                    const shapes = ['circle', 'square', 'triangle'];
                    const randomShape = shapes[Math.floor(Math.random() * shapes.length)];
                    obstacle.classList.add(randomShape);
                    const randomPosition = Math.floor(Math.random() * 380);
                    obstacle.style.left = randomPosition + 'px';
                    gameContainer.appendChild(obstacle);
                    const obstacleInterval = setInterval(function () {
                        const currentTop = parseInt(obstacle.style.top) || 0;
                        obstacle.style.top = (currentTop + 10) + 'px';
                        if (currentTop > 400) {
                            clearInterval(obstacleInterval);
                            gameContainer.removeChild(obstacle);
                        }
                        if (
                            currentTop + 20 >= 400 &&
                            playerPosition + 50 > parseInt(obstacle.style.left) &&
                            playerPosition < parseInt(obstacle.style.left) + 20
                        ) {
                            clearInterval(timerInterval);
                            endGame();
                        }
                    }, 50);
                    obstacleCount--;
                    setTimeout(createObstacle, Math.random() * 2000); // Spawn the next obstacle with a random delay
                }
            }
            createObstacle(); // Start spawning obstacles
        }
        // Function to end the game
        function endGame() {
            clearInterval(timerInterval);
            cancelAnimationFrame(animationFrameId);
            endTime = new Date().getTime();
            const survivalTime = (endTime - startTime) / 1000;
            alert('Game Over! You survived: ' + survivalTime.toFixed(2) + 's');
            location.reload();
        }
    </script>
</body>
</html>








