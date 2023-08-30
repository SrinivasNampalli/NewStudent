<!DOCTYPE html>
<html>
<head>
  <title>Student Blog</title>
  <style>
    .question {
      cursor: pointer;
      margin-bottom: 10px;
      font-weight: bold;
    }
    .answer {
      display: none;
    }
  </style>
  <script>
    function toggleAnswer(id) {
      var answer = document.getElementById(id);
      if (answer.style.display === "none") {
        answer.style.display = "block";
      } else {
        answer.style.display = "none";
      }
    }
  </script>
</head>
<body>
  <h1>Build your Home Page here</h1>
  
  <div>
    <img src="https://github.com/SrinivasNampalli/Srinivas-Nampalli1/assets/96441447/ad5f79c1-1e1c-4865-baa9-b4788d2c8dc1" alt="Ferrari F1" width="300" height="200">
    <p>
      Ferrari F1 embodies the pinnacle of speed, engineering, and passion. The team's legacy of excellence and pursuit of victory resonates deeply with me. Their precision and relentless drive inspire me to excel in every endeavor, mirroring their commitment to pushing boundaries and achieving greatness.
    </p>
  </div>

  <div>
    <img src="https://github.com/SrinivasNampalli/Srinivas-Nampalli1/assets/96441447/c78278eb-fda8-482d-8adc-4890617cceec" alt="Java" width="200" height="100">
    <p>
      Java is one of my favorite coding languages. I have been using it for a while and it will most likely always be the first choice whenever I decide to make any type of project.
    </p>
  </div>

  <div>
    <img src="https://github.com/SrinivasNampalli/Srinivas-Nampalli1/assets/96441447/0c561e08-0510-4cda-bf08-16b9c61406d3" alt="Chick-fil-A" width="150" height="100">
    <p>
      Chick-fil-A is my favorite fast food restaurant as I have been eating from there for a while now. My favorite item from their menu is their peach shake drink.
    </p>
  </div>

  <div>
    <img src="https://github.com/SrinivasNampalli/Srinivas-Nampalli1/assets/96441447/65b769de-58c7-47fe-9585-89c8e15b22d9" alt="Chrome Hearts" width="150" height="100">
    <p>
      Fashion is one of my favorite things because in my free time it's interesting to see what these famous designers are making. I like Nike and designer brands like Balenciaga due to how consistent they are at what they do.
    </p>
  </div>

  <h2>Quiz</h2>
  <div class="question" onclick="toggleAnswer('color')">What is my favorite color?</div>
  <div class="answer" id="color">My favorite color is blue.</div>
  
  <div class="question" onclick="toggleAnswer('brand')">What is my favorite fashion brand?</div>
  <div class="answer" id="brand">My favorite fashion brand is Chrome Hearts.</div>
  
  <div class="question" onclick="toggleAnswer('food')">What is my favorite fast food?</div>
  <div class="answer" id="food">My favorite fast food is Chick-fil-A.</div>

  <h2>Overview of Hacks, Study and Tangibles</h2>
  <p>
    Blogging in GitHub pages is a way to learn and code at the same time. Plans, lists, and scrum boards help you track key events, show progress, and record time. Effort is a big part of your class grade. Show plans and time spent! Hacks enable you to stay focused with key requirements of the class. Each hack will produce tangibles. Tangibles or tangible artifacts are things you accumulate as a learner and coder.
  </p>
  
  <table border="1">
    <tr>
      <th>Commands</th>
      <th>Definitions</th>
      <th>Week 0</th>
      <th>Week 1</th>
      <th>Week 2</th>
      <th>Week 3</th>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
