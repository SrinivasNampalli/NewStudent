---
comments: true
layout: post
title: StickFigure Game
description: Grab Calculator Code and place in IPYNB
type: tangibles
courses: { compsci: {week: 3} }
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stick Figure Running and Jumping Game</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            overflow: hidden;
        }
        #game-container {
            width: 100%;
            height: 400px;
            background-color: #87CEEB; /* Blue sky background */
            position: relative;
        }
#stick-figure {
            width: 50px;
            height: 100px;
            background-color: #000;
            position: absolute;
            bottom: 0;
            left: 50px;
            transition: transform 0.2s;
        }
        #ground {
            width: 100%;
            height: 20px;
            background-color: #008000; /* Green ground */
            position: absolute;
            bottom: 0;
        }
        .obstacle {
            width: 40px;
            height: 40px;
            background-color: #FF6347; /* Red */
            position: absolute;
            bottom: 20px;
        }
    </style>
</head>
<body>
    <div id="game-container">
        <div id="stick-figure"></div>
        <div id="ground"></div>
        <div class="obstacle" style="left: 300px;"></div>
        <div class="obstacle" style="left: 500px;"></div>
    </div>
</body>
</html>
