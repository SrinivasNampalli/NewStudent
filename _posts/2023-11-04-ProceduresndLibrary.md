---
comments: true
layout: post
title: P1 Procedures and Library
description: Ticket
type: hacks
courses: { compsci: {week: 10} }
---

<!DOCTYPE html>
<html>
<head>
    <title>Python Functions</title>
</head>
<body>
    <h2>Function 1: Procedural Abstraction</h2>
    <pre>
def procedural_abstraction(number1, number2):
    result = number1 * number2
    return result

x = 5
y = 7
product = procedural_abstraction(x, y)
print("The product of {} and {} is: {}".format(x, y, product))
    </pre>

    <h2>Function 2: Summing Machine</h2>
    <pre>
def summing_machine(first_number, second_number):
    result = first_number + second_number
    return result

sum_result = summing_machine(7, 5)
print("The sum of 7 and 5 is:", sum_result)
    </pre>
</body>
</html>
<html>
<head>
    <title>Python Libraries and API</title>
</head>
<body>
    <h1>Python Libraries:</h1>
    <ol>
        <li>
            <h2>NumPy:</h2>
            <p><strong>Purpose:</strong> NumPy is a fundamental library for scientific computing in Python. It provides support for large, multi-dimensional arrays and matrices, along with mathematical functions to operate on these arrays efficiently.</p>
            <p><strong>Favorite Variables/Functions:</strong></p>
            <ul>
                <li><code>np.array():</code> This function creates a NumPy array from a list or tuple, allowing you to perform element-wise operations on it.</li>
                <li><code>np.mean():</code> It calculates the mean or average of elements in an array, a valuable statistical function.</li>
            </ul>
        </li>
        <li>
            <h2>Pandas:</h2>
            <p><strong>Purpose:</strong> Pandas is a data manipulation library that provides data structures for efficiently storing large datasets and tools for data analysis. It's commonly used for working with structured data.</p>
            <p><strong>Favorite Variables/Functions:</strong></p>
            <ul>
                <li><code>DataFrame:</code> A core data structure in Pandas, it allows you to store and manipulate data in a tabular form.</li>
                <li><code>read_csv():</code> This function reads data from a CSV file and creates a DataFrame, making it easy to work with structured data.</li>
            </ul>
        </li>
        <li>
            <h2>Matplotlib:</h2>
            <p><strong>Purpose:</strong> Matplotlib is a popular data visualization library. It enables users to create various types of plots and charts to visualize data.</p>
            <p><strong>Favorite Variables/Functions:</strong></p>
            <ul>
                <li><code>plt.plot():</code> This function is used to create line plots, which are essential for visualizing trends and patterns in data.</li>
                <li><code>plt.xlabel():</code> It sets the label for the x-axis, making the plot more informative.</li>
            </ul>
        </li>
    </ol>
    <h1>API: Google Maps API</h1>
    <p><strong>Type:</strong> Google Maps API is a RESTful web service API.</p>
    <p><strong>Purpose:</strong> It provides access to various Google Maps services, allowing developers to integrate location-based services, mapping, and geocoding into their applications.</p>
    <p><strong>Unique Feature:</strong> One unique feature is the "Directions API," which not only provides directions from one location to another but also offers multiple modes of transportation (e.g., driving, walking, or bicycling) and even suggests alternate routes.</p>
    <p><strong>Scenario:</strong> Imagine you are developing a travel app. You can use the Google Maps API to provide users with directions and estimated travel times based on their selected mode of transportation. Users can also explore nearby places of interest.</p>
    <h1>Data Manipulation Library: Pandas</h1>
    <p><strong>Prefixed Function/Variable with Comments:</strong></p>
    <pre>
        <code>
import pandas as pd

# Create a DataFrame from a dictionary
data = {'Name': ['Alice', 'Bob', 'Charlie'],
        'Age': [25, 30, 28]}
df = pd.DataFrame(data)

# Print the DataFrame
print(df)
        </code>
    </pre>
    <p>In this code snippet, we import the Pandas library as pd. We create a DataFrame from a dictionary, data, and then print the DataFrame. DataFrames are a powerful way to work with structured data, and Pandas provides numerous functions for data manipulation and analysis.</p>
</body>
</html>
