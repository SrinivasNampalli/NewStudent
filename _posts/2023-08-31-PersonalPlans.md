---
toc: true
comments: false
layout: post
title: Personal Projects
description: Cools features that involve project tracking.
type: plans
courses: { compsci: {week: 2} }
---

### Plans
<html>
<head>
  <title>Task Manager</title>
  <style>
    select, button {
      margin: 10px;
    }
    
    ul {
      list-style-type: none;
    }
    
    li {
      display: flex;
      align-items: center;
      margin-bottom: 10px;
    }
    
    input[type="checkbox"] {
      margin-right: 10px;
    }
    
    label {
      cursor: pointer;
    }
    
    .completed {
      text-decoration: line-through;
      color: gray;
    }
  </style>
  <script>
    function addTask() {
      const taskText = prompt("Enter task name:");
      if (taskText) {
        const taskList = document.getElementById("taskList");
        const taskItem = document.createElement("li");
        taskItem.innerHTML = `
          <input type="checkbox">
          <label>${taskText}</label>
          <button onclick="removeTask(this.parentNode)">Delete</button>
        `;
        taskList.appendChild(taskItem);
      }
    }

    function removeTask(taskItem) {
      taskItem.parentNode.removeChild(taskItem);
    }
  </script>
</head>
<body>
  <h1>Task Manager</h1>
  <select id="weekSelect">
    <option value="week1">Week 1</option>
    <option value="week2">Week 2</option>
    <option value="week3">Week 3</option>
    <!-- Add more weeks here -->
  </select>

  <button onclick="addTask()">Add Task</button>
  
  <ul id="taskList">
    <!-- Tasks will be added dynamically here -->
  </ul>
</body>
</html>
<html>
<head>
  <title>My Plans Checklist</title>
  <style>
    ul {
      list-style-type: none;
    }
    
    li {
      display: flex;
      align-items: center;
      margin-bottom: 10px;
    }
    
    input[type="checkbox"] {
      margin-right: 10px;
    }
    
    label {
      cursor: pointer;
    }
    
    .completed {
      text-decoration: line-through;
      color: gray;
    }
  </style>
  <script>
    function toggleComplete(task) {
      task.classList.toggle("completed");
    }
  </script>
</head>
<body>
  <h1>My Plans Checklist</h1>
  <ul>
    <li onclick="toggleComplete(this)">
      <input type="checkbox">
      <label>Learn basics of python and advance my skills in HTMl and Javascript</label>
    </li>
    <li onclick="toggleComplete(this)">
      <input type="checkbox">
      <label>Finish making the quiz</label>
    </li>
    <li onclick="toggleComplete(this)">
      <input type="checkbox">
      <label>Complete coding project</label>
    </li>
    <!-- Add more plans here -->
  </ul>
</body>
</html>

