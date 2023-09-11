---
comments: true
layout: post
title: Review Ticket
description: Ticket
type: tangibles
courses: { compsci: {week: 3} }
---


- Variables & Data Structures: Variables are used to store data. Python supports various data types, including integers, floating-point numbers, strings, lists, tuples, dictionaries, sets, and more.
- Comments: Comments in Python are marked using the # symbol. They are used to provide explanations and make code more understandable.
```
#This is a comment
```
```
Some data structures:
- tuple: (20, 'mark', 43.5, [30,60,90])
- dictionary: {'b':5,'c':7,'d':12}
- list: [1,2,3]
```
As you can see above, I've shown how to comment out lines with a hashtag. I've also depicted the three main data structures: tuples, dictionaries, and lists. In the tuple shown above, 20 would be term 0, and 'mark' would be term 1. This also applies in the list, since '1' is term 0, not term 1. Lastly, the dictionary is full of pairs of keys and values, with the key being 'b', and b's value being 5.
- There are two types of loops in python known as the for loop and while loop. A "for" loop is used to iterate over a sequence or any iterable object, and executes a block of code for each item in the sequence. A "while" loop is used to repeatedly run a block of code, until a condition is met.
```
for item in iterable:
    # Code to repeat for each item in the iterable
i = 0
while(i <= 10):
    print(i)
    i = i + 1
```
Above we can see both of the loops in action.
- There are conditional statements in python, in which certain blocks of code are ran, dependent on whether or not a condition is true. The conditional statements are elif, if, and else.
```
if condition:
    # Code to execute if condition is True
elif another_condition:
    # Code to execute if an other condition is true
else:
    # Code to execute if other condtions aren't True
```
- Functions: Functions help you bundle certain blocks of code that you can reuse later in your program. You can define a function by typing the word "def", before typing all the code that you want to be included in the function.
```
def multiplication(n1, n2):
    return n1 * n2
print(multiplication(5,3))
```
Although defining a function may feel useless, in many scenarios it can save you from writing a lot of code, and save space.
### HTML Structure
- In HTML, the <div> element is a container that is often used to group and structure content on a web page. The name "div" stands for "division," and it is one of the most commonly used HTML elements for creating layouts and organizing content. The <div> element itself doesn't have any meaning, its purpose is to provide a way to group together and apply styling or scripting to a set of HTML elements.
```
<div>
    <h1>This is Anvay and Srini's website</h1>
    <p>main content goes here</p>
</div>
```
- In HTML, the script element is used to embed or reference client-side JavaScript code within an HTML document. Java script allows you to perform various tasks on a web page.
Attributes:
src: Specifies an external JavaScript file to be linked.
type: Specifies the scripting language (usually set to "text/javascript").
Example of inline script:
- example of inline script
```
<script type="text/javascript">
    // JavaScript code here
    console.log("Hello, world!");
</script>
```
```
<script src="script.js" type="text/javascript"></script>
```
- In HTML, Description: The input element is used to create interactive form controls that allow users to input data. It can be used to create various types of input fields such as text boxes, checkboxes, radio buttons, and more.
Common attributes:
type: Specifies the type of input control (e.g., "text", "checkbox", "radio", "submit").
name: Provides a name for the input element, which is used when submitting form data.
value: Sets the initial value of the input element.
```
<input type="text" name="username" placeholder="Enter your username">
```
- Above there's an example of text input
```
<input type="checkbox" name="subscribe" value="yes"> Subscribe to newsletter
```
- Above there's an example of a checkbox
- Description: The span element is an inline-level container used to apply styling or scripting to a specific portion of text or content within a larger block of text. It is often used to target and style specific words or phrases within paragraphs or headings.
```
.highlighted {
    background-color: yellow;
    font-weight: bold;
}
```
The script, input, and span elements are fundamental to creating interactive and dynamic web pages.






