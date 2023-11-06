---
comments: true
layout: post
title: MachineLearning Code(Collaboration)
description: Ticket
type: tangibles
courses: { compsci: {week: 9} }
---
 <!DOCTYPE html>
<html>
<head>
    <title>Machine Learning Model Evaluation</title>
</head>
<body>
    <h1>Machine Learning Model Evaluation</h1>

    <h2>Model Evaluation and Prediction</h2>

    <p>This code represents a machine learning model evaluation and prediction process. It involves the use of regression techniques for predicting outcomes based on input features, such as GPA and SAT scores. The code utilizes the scikit-learn library for regression.</p>

    <h3>Evaluation</h3>

    <p>The model is first evaluated using a testing dataset. It calculates two performance metrics:</p>
    <ul>
        <li>Mean Absolute Error (MAE): A metric that measures the average absolute difference between the actual and predicted values. A lower MAE indicates a better model fit.</li>
        <li>R-squared (R2) Score: A metric that measures the proportion of the variance in the dependent variable that is predictable from the independent variables. It ranges from 0 to 1, with higher values indicating a better fit.</li>
    </ul>

    <p>The evaluation results are printed to the console for analysis.</p>

    <h3>Prediction</h3>

    <p>After the model is evaluated, it can be used for making predictions. The <code>predict</code> method takes GPA and SAT scores as input and predicts an outcome based on the trained model. The predicted value is then returned.</p>

    <h3>Usage</h3>

    <p>To use this model, an instance of the <code>RecEngine</code> class is created. In this instance, the <code>predict</code> method is called with specific GPA and SAT values (4.0 and 1600 in this example). The predicted value is printed to the console.</p>

    <pre><code>
from sklearn import metrics
import pandas as pd

class RecEngine:
    # ... (code not shown for brevity)

model = RecEngine()
prediction = model.predict(4.0, 1600)
print(f"The predicted value is {prediction}")
     
    def buildModel(self):
        basedir = os.path.abspath(os.path.dirname(__file__))

        # Specify the file path
        file_path = basedir + "/../static/data/MLData.csv"

        dataset = pd.read_csv(file_path, header=0)
        array = dataset.values

        x = array[:, 0:2]
        y = array[:, 2]

        X_Train, X_Test, Y_Train, Y_Test = train_test_split(x, y, test_size=0.2, random_state=0)
    </code></pre>

    <p>Overall, this code snippet demonstrates how machine learning models can be evaluated and used for predictions based on regression analysis. It's a valuable process for various applications, including predicting outcomes like grades, sales, or any other numerical values.</p>
</body>
</html>
