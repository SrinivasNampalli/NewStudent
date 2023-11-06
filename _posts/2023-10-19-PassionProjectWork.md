---
comments: true
layout: post
title: GPA and SAT(Important Commit)
description: Ticket
type: tangibles
courses: { compsci: {week: 8} }
---
<<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GPA & SAT Form</title>
    <style>
        .container {
            text-align: center;
            margin-top: 50px;
        }
        .box {
            width: 200px;
            height: 80px;
            background-color: lightblue;
            margin: 20px auto;
            padding: 10px;
            cursor: pointer;
            transition: transform 0.2s;
        }
        .box:hover {
            transform: scale(1.05);
        }
        .message {
            display: none;
            font-size: 18px;
            margin-top: 20px;
        }

        input {
            width: 80%;
            padding: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="box" id="gpa-box" onclick="animateBox('gpa')">
            GPA: <input type="number" id="gpa" placeholder="Enter GPA">
        </div>
        <div class="box" id="sat-box" onclick="animateBox('sat')">
            SAT: <input type="number" id="sat" placeholder="Enter SAT">
        </div>
        <button onclick="showFitCollegeMessage()">Submit</button>
        <div class="message" id="message">Generating a fit college for you</div>
        <div class="message" id="question"></div>
    </div>
    <script>
        let gpaSubmitted = false;
        let satSubmitted = false;
        function animateBox(type) {
            const box = document.getElementById(`${type}-box`);
            if (type === 'gpa' && !gpaSubmitted) {
                // Implement your animation here
                box.style.backgroundColor = 'lightgreen';
                gpaSubmitted = true;
            } else if (type === 'sat' && !satSubmitted) {
                // Implement your animation here
                box.style.backgroundColor = 'lightgreen';
                satSubmitted = true;
            }
        }
        function showFitCollegeMessage() {
            const message = document.getElementById('message');
            const question = document.getElementById('question');
            if (gpaSubmitted && satSubmitted) {
                message.style.display = 'block';
                const questions = [
                    'What\'s your preferred major?',
                    'Do you have a specific location in mind?',
                    'Are you interested in extracurricular activities?',
                    'Tell us about your career goals.'
                ];
                const randomQuestion = questions[Math.floor(Math.random() * questions.length)];
                question.textContent = randomQuestion;
            }
        }
    </script>
</body>
</html>


###ReflectionFirstCommit
TheHTML code is well-structured, creating a user-friendly GPA and SAT input interface. The interactive boxes' hover animation provides a visual cue for users. The JavaScript functions manage user input and display relevant messages effectively. Once both GPA and SAT scores are submitted, the code prompts users with questions related to college preferences, enhancing user engagement. This was my first prototype 