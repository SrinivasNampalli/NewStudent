---
comments: true
layout: post
title: P1 Lists and Search and Developing Algorithm
description: Ticket
type: hacks
courses: { compsci: {week: 9} }
---
<html>
<head>
    <title>Python Code</title>
</head>
<body>
    <h1>Python Code for Lists, Search, and Algorithm</h1>

    <h2>Append, Remove, Index, and Count</h2>
    <pre>
# Append a new number (110) to the end of the list
numbers.append(110)

# Remove the element at index 4 (number 50)
removed_element = numbers.pop(4)

# Print the modified list
print("Updated list:", numbers)

# Find the index of a specific number (70)
index = numbers.index(70)
print("Index of 70:", index)

# Count the occurrences of a number (70) in the list
count = numbers.count(70)
print("Occurrences of 70:", count)
    </pre>

    <h2>Homework #2 - Binary Search Iterations and Median</h2>
    <pre>
# Homework #2
def worst_case_binary_search_iterations(array_length):
    low = 0
    high = array_length - 1
    target = array_length  # This is an item not present in the array
    iterations = 0

    while low <= high:
        mid = (low + high) // 2
        if target == mid:
            return iterations
        elif target < mid:
            high = mid - 1
        else:
            low = mid + 1
        iterations += 1

    return iterations

array_length = 20
iterations = worst_case_binary_search_iterations(array_length)
print(f"Worst-case iterations for an array of length {array_length}: {iterations}")

def find_median(grades):
    sorted_grades = sorted(grades)
    n = len(sorted_grades)
    if n % 2 == 1:
        # Odd number of grades
        median = sorted_grades[n // 2]
    else:
        middle1 = sorted_grades[n // 2 - 1]
        middle2 = sorted_grades[n // 2]
        median = (middle1 + middle2) / 2
    return median

test_grades = [85, 92, 78, 90, 88, 95]
median_grade = find_median(test_grades)
print(f"The median test grade is: {median_grade}")
    </pre>

    <h2>Dice Rolling Game</h2>
    <pre>
# 2
import random

def roll_dice():
    return random.randint(1, 6)

def play_game():
    while True:
        input("Press Enter to roll the dice...")
        dice1 = roll_dice()
        dice2 = roll_dice()
        total = dice1 + dice2
        print(f"You rolled a {dice1} and a {dice2}. Total: {total}")

        if total == 7:
            print("You win!")
        else:
            print("You lose. Try again.")

        play_again = input("Play again? (yes/no): ").lower()
        if play_again != "yes":
            print("Thanks for playing!")
            break

if __name__ == "main":
    print("Welcome to the Dice Rolling Game!")
    play_game()
    </pre>
</body>
</html>
