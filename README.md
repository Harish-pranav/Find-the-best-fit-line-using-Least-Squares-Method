# Implementation of Univariate Linear Regression
## AIM:
To implement univariate Linear Regression to fit a straight line using least squares.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Get the independent variable X and dependent variable Y.
2. Calculate the mean of the X -values and the mean of the Y -values.
3. Find the slope m of the line of best fit using the formula. 
<img width="231" alt="image" src="https://user-images.githubusercontent.com/93026020/192078527-b3b5ee3e-992f-46c4-865b-3b7ce4ac54ad.png">
4. Compute the y -intercept of the line by using the formula:
<img width="148" alt="image" src="https://user-images.githubusercontent.com/93026020/192078545-79d70b90-7e9d-4b85-9f8b-9d7548a4c5a4.png">
5. Use the slope m and the y -intercept to form the equation of the line.
6. Obtain the straight line equation Y=mX+b and plot the scatterplot.

## Program:

```

Program to implement univariate Linear Regression to fit a straight line using least squares.
Developed by: HARISH PRANAV 
RegisterNumber:  212224040117

```
```
import numpy as np
import matplotlib.pyplot as plt

# Independent variable (X) and dependent variable (Y)
X = np.array([1, 2, 3, 4, 5], dtype=float)
Y = np.array([2, 4, 5, 4, 5], dtype=float)

# Check that the data is valid
if len(X) != len(Y) or len(X) < 2:
    raise ValueError("X and Y must have the same length and at least two values.")

if np.all(X == X[0]):
    raise ValueError("X values must not all be identical.")

# Calculate the means
x_mean = np.mean(X)
y_mean = np.mean(Y)

# Calculate slope (m) using least squares
m = np.sum((X - x_mean) * (Y - y_mean)) / np.sum((X - x_mean) ** 2)

# Calculate y-intercept (b)
b = y_mean - m * x_mean

# Predicted Y values
Y_pred = m * X + b

# Display the results
print(f"Slope (m): {m:.4f}")
print(f"Y-intercept (b): {b:.4f}")
print(f"Regression equation: Y = {m:.4f}X + {b:.4f}")

# Plot the data and regression line
plt.scatter(X, Y, color="blue", label="Observed data")
plt.plot(X, Y_pred, color="red", label="Least-squares regression line")
plt.xlabel("X")
plt.ylabel("Y")
plt.title("Univariate Linear Regression")
plt.legend()
plt.grid(True)
plt.show()
```

## Output:
<img width="1418" height="660" alt="image" src="https://github.com/user-attachments/assets/5cc523f3-7b57-4457-ac4e-f060a7ecf6ae" />



## Result:
Thus the univariate Linear Regression was implemented to fit a straight line using least squares using python programming.
