## **Data Preparation and Exploratory Data Analysis**

### Exploratory Data Analysis
- Exploring and visualizing data to find useful patterns and insights that help inform the modelling process.
- EDA lets you identify the most promising features of your model.
- It helps to uncover potential issues with the features or targets that need to be addressed.

### **EDA** for **Regression**
- Target variable
- Features
- Feature Target Relationship
- Feature Feature Relationship

### Exploring Target Variable
- Understand where most values lie (Mean, Median, and Mode)
- How spread out they are (Range, Variance, Standard Deviation)
- What shape? or Distribution?
- Outliers?
- Data Visualization (Histogram, Boxplot, Skewness)
- Right Skewed (Positive Skewed: Mean > Median > Mode)
- Left Skewed (Negative Skewed: Mode > Median > Mean)
- Symmetrical (Normal: Mean = Median = Mode)

```python
import seaborn as sns

# Histogram Plot: (Check the skewness)
sns.histplot(diamonds['price']);

# Boxplot: (Check outliers and median)
sns.boxplot(x = diamonds['price'])

# Remove the top and right borders:
sns.despine();
```      

### Exploring the Features
- Helps us understand them and start to understand the transformation we need to apply to each one.
- Histograms and boxplots (Numeric Features)
- **value_counts()** and bar charts (Categorical Features)

### Linear Relationships
- Numeric variables have linear relationships between them (positive, negative, no relationship)
- Positive relationship (One changes, other changes in the same direction)
- Negative relationship (One changes, other changes in opposite direction)
- When one variable changes, so does the other
- These relationships can be visualized with scatterplots and heatmaps (Correlation Matrix)
```python
sns.scatterplot(data=ads, x='digital_spend', y='site_traffic');
```
- **Correlation:** Measure the strength and direction of a linear relationship

```python
# Calculate correlations between two columns:
df['column 1'].corr(df['column 2'])
```  

Range | Correlation 
:--- | :---:
-1 to -0.9 | Very Strong (Negative)
-0.9 to -0.7 | Strong (Negative)
-0.7 to -0.4 | Moderate (Negative)
-0.4 to -0.1 | Weak (Negative)
-0.1 to 0.1 | None (Negative)
0.1 to 0.4 | Weak (Positive)
0.4 to 0.7 | Moderate (Positive)
0.7 to 0.9 | Strong (Positive)
0.9 to 1 | Very Strong (Positive)

- **Correlation Matrix:** Correlation between each column in a DataFrame
```python
# Correlation matrix:
df.corr(numeric_only = True)

# Heatmap:
sns.heatmap(df.corr(numeric_only = True), annot = True);
```

### Feature Target Relationships
- Helps identify potentially useful features for our model
- Scatterplot, Boxplot, Histogram: Explore numeric features
- Bar Charts: Explore categorical features
- Features that have a high correlation with the target is good for prediction

### Feature Feature Relationships
- Helps identify highly correlated features, which can cause problems with regression models
- Removing one feature will solve the problem
- Features that have a high correlation with each other (feature) can cause problems in a model

### Preparing for Modeling
- Structuring the data as a valid input for a model
- Stored in a single table (DataFrame)
- Aggregated to the right grain (1 row per target)
- Non-null (No missing value)
- Data type should be converted to numeric (Categorical features should be encoded)
