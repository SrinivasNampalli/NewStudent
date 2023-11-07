---
comments: true
layout: post
title: Reflection(Lists and Searching)
description: Ticket
type: tangibles
courses: { compsci: {week: 9} }
---
<html>
<head>
    <title>Reflection on Recursion and Iteration</title>
</head>
<body>
    <p>
        Recursion and iteration are fundamental concepts in programming, each with its unique strengths and use cases. Recursion involves a function calling itself to solve a problem, breaking it down into simpler subproblems. It often leads to elegant and concise code but can be less efficient due to multiple function calls. Iteration, on the other hand, uses loops to repeat a set of instructions, making it more efficient and easier to understand for many tasks.
    </p>
    <p>
        Choosing between recursion and iteration depends on the problem's nature and complexity. Recursion is well-suited for problems with a recursive structure, while iteration shines when simplicity, performance, and predictability are essential. Understanding both approaches equips a programmer with versatile problem-solving tools for different situations.
        <pre>
<code>
This is my code
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1  # Element not found

my_list = [4, 2, 9, 7, 1, 6]
element_to_find = 9
result = linear_search(my_list, element_to_find)
if result != -1:
    print(f"Element {element_to_find} found at index {result}.")
else:
    print(f"Element {element_to_find} not found."
</code>
</pre>
<pre>
<code>
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1  # Element not found

sorted_list = [1, 2, 4, 6, 7, 9]
element_to_find = 4
result = binary_search(sorted_list, element_to_find)
if result != -1:
    print(f"Element {element_to_find} found at index {result}.")
else:
    print(f"Element {element_to_find} not found."
</code>
</pre>
<pre>
<code>
my_list = [3, 1, 5, 2, 4]
my_list.sort()
print("Sorted list:", my_list)
</code>
</pre>
<pre>
<code>
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_numbers = [x for x in numbers if x % 2 == 0]
print("Even numbers:", even_numbers)
</code>
</pre>

    </p>
</body>
</html>
