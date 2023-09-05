---
toc: true
comments: false
layout: post
title: Basic Search Engine
description: Nice things that I can update and add too.
type: hacks
courses: { compsci: {week: 2} }
---
<!DOCTYPE html>
<html>
<head>
  <title>Random Response Generator</title>
</head>
<body>
  <h1>Ask Me Anything</h1>
  
  <input type="text" id="question" placeholder="Ask a question...">
  <button onclick="generateResponse()">Ask</button>
  
  <p id="response"></p>
  
  <script>
    const responses = [
      "Yes, definitely.",
      "No, absolutely not.",
      "I'm not sure. Ask again later.",
      "It's possible.",
      "I doubt it.",
      "Certainly!",
      "I'm sorry, I can't answer that.",
    ];

    function generateResponse() {
      const question = document.getElementById("question").value;
      const responseElement = document.getElementById("response");
      
      // Generate a random response from the array
      const randomIndex = Math.floor(Math.random() * responses.length);
      const randomResponse = responses[randomIndex];

      // Display the response
      responseElement.textContent = `Response: ${randomResponse}`;
    }
  </script>
</body>
</html>
