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
  <title>Basic Search Algorithm</title>
</head>
<body>
  <h1>Basic Search Algorithm</h1>
  
  <input type="text" id="searchInput" placeholder="Enter a value...">
  <button onclick="search()">Search</button>
  
  <p id="result"></p>
  
  <script>
    const data = [12, 45, 78, 23, 56, 90, 34, 67, 89, 32];

    function search() {
      const searchValue = parseInt(document.getElementById("searchInput").value);
      const resultElement = document.getElementById("result");
      const index = linearSearch(data, searchValue);

      if (index !== -1) {
        resultElement.textContent = `Found at index ${index}.`;
      } else {
        resultElement.textContent = `Not found.`;
      }
    }

    function linearSearch(array, value) {
      for (let i = 0; i < array.length; i++) {
        if (array[i] === value) {
          return i;
        }
      }
      return -1;
    }
  </script>
</body>
</html>

