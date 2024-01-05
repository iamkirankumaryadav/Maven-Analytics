## **Simple Linear Regression**

- **Simple linear regression** models use a single **feature** to **predict** the **target**.
- This is achieved by fitting a line through the data points in a **scatterplot**
- Predicted value for the target = (Slope of the relationship * Value for feature) + The y-intercept 
- Error / Residual: Difference between the actual and predicted values.

### **Least Squared Error**
- Finds the best-fit line for data.

### **R Squared | Coefficient of determination**
- Measures how much better the model is at predicting the target using its mean (Best guess without using features)
- R squared values range between 0 and 1

**SSE** (Sum of squared error: Distance between values and line)

**SST** (Sum of squared total: Distance between values and mean)

### **Hypothesis Test**
- Regression models include several hypothesis tests, including the F test, that indicate whether our model is significantly better at predicting our target than using the mean of the target as the model

Steps:
1. State the null (H0) and alternative (Ha) hypothesis
2. Set a significance level (alpha)
3. Calculate the test statistic and p-value.
4. Conclude test:
-- If **p-value <= alpha**, reject the null hypothesis (Model is useless)
-- If **p-value > alpha**, don't reject (Model needs more training)

    
