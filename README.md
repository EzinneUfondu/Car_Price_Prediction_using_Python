# Car_Price_Prediction_using_Python
This project demonstrates how numerical vehicle features can be used to predict prices and classify vehicles into market segments.

📘 Automobile Price Prediction & Classification

A machine learning project that predicts automobile prices using numerical vehicle features and classifies cars into low, medium, and high price categories. This project demonstrates data cleaning, exploratory data analysis (EDA), feature engineering, regression modelling, classification, and model evaluation.

🤖Project Overview
This project uses the Automobile Dataset to explore how vehicle characteristics influence price. The workflow includes:
Cleaning missing and inconsistent data
Converting data types
Exploratory data analysis with summary statistics, correlations, and boxplots
Feature selection
Building regression models (Linear Regression & Random Forest)
Building a classification model (Logistic Regression)
Comparing train–test splits (80/20 vs 70/30)
Extracting business insights
The goal is to understand which features drive price and how well different models can predict or classify vehicle prices.

📂 Dataset
The dataset contains numerical and categorical attributes such as:
Engine size
Horsepower
Curb weight
Width
Fuel type
Body style
Price
Missing values were represented with "?" and replaced with NaN before type conversion.
🧹 Data Cleaning
Key cleaning steps:
Replaced "?" with NaN
Converted numerical columns using pd.to_numeric(errors="coerce")
Removed rows with missing target values
Ensured all selected features were numeric
📊 Exploratory Data Analysis (EDA)
EDA included:
Summary statistics (df.describe())
Correlation heatmap to identify strong predictors
Boxplots to examine distributions and detect outliers
Outliers were retained because they represented real high‑performance vehicles
🛠 Feature Engineering
For regression, four numerical features were selected:
Engine size
Horsepower
Curb weight
Width
For classification, price was binned into low, medium, and high using qcut.
Why binning matters:  
Binning prevents class imbalance, ensures fair representation of each price group, and improves classification stability.
🤖 Models Used
Linear Regression
Baseline model
Simple and interpretable
Performance dropped slightly when training data was reduced (70/30 split)
Random Forest Regression
Best performing model
Captured non‑linear relationships
Stable across both 80/20 and 70/30 splits
Logistic Regression (Classification)
Used to classify cars into price categories
Performed well with balanced bins
🏋️‍♀️ Train–Test Split Comparison
Two splits were tested:
80/20 (standard)
70/30 (larger test set)
Findings:
Linear Regression became less stable with 70/30
Random Forest remained consistent across both splits
Ensemble models handle data variation better
📈 Visuals (Screenshots to Include)
Summary statistics
Correlation heatmap
Boxplots of numerical features
Actual vs predicted scatter plot (Linear Regression)
Random Forest results
Logistic Regression confusion matrix
70/30 split results
💼 Business Insights
Key insights for manufacturers and dealerships:
Performance‑related features (engine size, horsepower, curb weight, width) strongly influence price
Random Forest provides reliable pricing predictions even when data availability changes
Classification helps segment vehicles into meaningful market categories
Robust models support better pricing strategies and market positioning
🧾 Conclusion
This project demonstrates how numerical vehicle features can be used to predict prices and classify vehicles into market segments. Random Forest proved to be the most reliable model, showing strong performance and stability across different train-test splits. The classification model further supported segmentation strategies by accurately grouping vehicles into price categories. Overall, the project highlights the value of machine learning in supporting data‑driven pricing decisions.
📚 Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit‑learn
