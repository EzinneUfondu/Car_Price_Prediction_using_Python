# Car_Price_Prediction_using_Python
This project demonstrates how numerical vehicle features can be used to predict prices and classify vehicles into market segments.

A machine learning project that predicts automobile prices based on technical specifications and physical features, using the UCI Automobile dataset.


## Overview

Car pricing is influenced by a combination of performance metrics, engine specifications, and physical dimensions. This project applies data analytics and machine learning to explore those relationships and build models that can predict car prices — both as a continuous value and as a category (Low, Medium, High).

The project was completed as part of the Fundamentals of Data Analytics module (MSc Data Analytics, BSBI / University for the Creative Arts, 2026).


## Dataset

- **Source:** UCI Machine Learning Repository via IBM Developer Skills Network
- **URL:** https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DA0101ENSkillsNetwork/labs/Data%20files/auto.csv
- **Size:** 205 rows, 26 features
- **Target Variable:** `price`

Key features used in modelling: `engine-size`, `horsepower`, `curb-weight`, `width`


## Methods

### 1. Data Cleaning
- Replaced `"?"` with `NaN` for proper missing value handling
- Converted `price` and `horsepower` to numeric (float)
- Dropped rows with missing values in key modelling columns

### 2. Exploratory Data Analysis (EDA)
- Descriptive statistics: mean, median, standard deviation
- Correlation heatmap to identify features most related to price
- Boxplot: Price vs Body Style
- Histogram: Price and Horsepower distributions
- Scatter plots: Individual feature relationships with price

### 3. Feature Engineering
- Created `city-L/100km` column: `235 / city-mpg`
- Applied horsepower binning: Low / Medium / High
- Normalised selected features

### 4. Model Development

**Regression (predicting continuous price):**
- Linear Regression — baseline model
- Random Forest Regressor — ensemble model
- Tested two train/test splits: 80/20 and 70/30

**Classification (predicting price category):**
- Price binned into Low, Medium, High using `pd.qcut()`
- Logistic Regression classifier (~82% accuracy)

### 5. Evaluation Metrics
- R² Score
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Accuracy score and Confusion Matrix (classification)


## Results

| Model | Split | R² Score |
|---|---|---|
| Linear Regression | 80/20 | ~0.764 |
| Linear Regression | 70/30 | ~0.782 |
| Random Forest Regressor | 80/20 | Higher & more stable |
| Logistic Regression (Classification) | 80/20 | ~82% accuracy |

**Key findings:**
- Engine size, horsepower, curb weight, and width were the strongest predictors of price
- Random Forest outperformed Linear Regression and remained stable across both splits
- Logistic Regression successfully classified cars into price categories with ~82% accuracy



## Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.linear_model import LinearRegression, LogisticRegression
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score, accuracy_score, confusion_matrix
```



## Author

**Ezinne Ufondu**
MSc Data Analytics | BSBI Berlin
[LinkedIn](https://linkedin.com/in/ezinneufondu) | [GitHub](https://github.com/EzinneUfondu)
