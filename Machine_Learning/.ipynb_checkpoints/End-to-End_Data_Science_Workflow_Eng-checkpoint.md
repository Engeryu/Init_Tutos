# 📊 End-to-End Data Science Workflow  
**Author:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

Voici la version française du document [End-to-End Data Science Workflow](./End-to-End_Data_Science_Workflow_FR.md)  
This document is the last of a series:
- [SQL_CheatSheet_Eng.ipynb](./SQL_CheatSheet_Eng.md)
- [Python_Pandas_Eng.ipynb](./Python_Pandas_CheatSheet_Eng.md)
- [Numpy_Pandas_Eng](./NumPy_Pandas_CheatSheet_Eng.md)
- [Data_Preprocessing_Methods_Eng.ipynb](./Data_Preprocessing_Methods_Eng.md)

# 🧠 Dynamic Table of Contents
1. [🧭 I. Subject Introduction](#🧭-I.-Subject-Introduction)  
   - [1.1. Context of the Study / Objectives / Research Questions](#1.1.-Context-of-the-Study-/-Objectives-/-Research-Questions)  
   - [1.2. Constraints and Limitations](#1.2.-Constraints-and-Limitations)  
2. [🗂️ II. Environment Setup](#🗂️-II.-Environment-Setup)  
   - [2.1. Imports](#2.1.-Imports)  
   - [2.1.1. Libraries](#2.1.1.-Libraries)  
   - [2.1.2. Dataset Loading](#2.1.2.-Dataset-Loading)  
   - [👁️ 2.2. Initial Exploration - Basic Dataset Structure Overview](#👁️-2.2.-Initial-Exploration---Basic-Dataset-Structure-Overview)  
3. [🧹 III. Data Cleaning and Transformation - Handling polluted data](#🧹-III.-Data-Cleaning-and-Transformation---Handling-polluted-Data)  
4. [🧠 IV. Feature Engineering](#🧠-IV.-Feature-Engineering)  
5. [📈 V. Exploratory Data Analysis - EDA](#📈-V.-Exploratory-Data-Analysis---EDA)  
6. [🧪 VI. Inferential Analysis](#🧪-VI.-Inferential-Analysis)  
7. [🤖 VII. Predictive Modeling](#🤖-VII.-Predictive-Modeling)  
8. [📌 VIII. Prescriptive Analysis](#📌-VIII.-Prescriptive-Analysis)  

---

## 🧭 I. Subject Introduction  
### 1.1. Context of the Study / Objectives / Research Questions
Why did you choose this dataset ? What are the stakeholders ? What are deliverables at the end ?
### 1.2. Constraints and Limitations  
- Planning of your deadline / How much time to work on it.  
- Ressources Compute, Data Quality and Graniness
---

## 🗂️ II. Environment Setup
### 2.1. Imports
#### 2.1.1. Libraries  
```python
# Import necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px

# Import the secondary libraries
from sklearn.sublibraries import MachineLearningsTools as mltools...
from scipy.sublibrairies import MathsTools as mathtools...
from datetime import date, datetime...

# Import the support libraries
```  
#### 2.1.2. Dataset Loading  
```python
# Load the dataset into a Pandas DataFrame
df = pd.read_csv('your_dataset.csv') # To read CSV file

# Read data from a URL
df_url = pd.read_csv('https://example.com/your_data.csv') # To read data from a URL

# Read Excel file
df_excel = pd.read_excel('your_file.xlsx', sheet_name='Sheet1') # To read Excel file

# Read JSON file
df_json = pd.read_json('your_file.json') # To read JSON file

# Read SQLite File
import sqlite3
con = sqlite3.connect("database.sqlite") # Connect Jupyter to database.sqlite
df = pd.read_sql_query("SELECT * from table", con) # Create DataFrame from SQL query into last variable

# Read SQL File (Same as last example, with another API)
from sqlalchemy import create_engine # To insert in the secondary libraries
engine = create_engine('sqlite:///your_database.db')      # Create a SQLite database engine
df_sql = pd.read_sql('SELECT * FROM your_table', engine)  # Read data from a SQL table

# Verify that result of SQL query is stored in the dataframe
print(df.head())

# Read Parquet file
df_parquet = pd.read_parquet('your_file.parquet') # To read Parquet file

# The file type above are the main file types you will encounter in Data Science. But here are some other file types below such as :

# Read HDF5 file
df_hdf5 = pd.read_hdf('your_file.h5', key='your_key') # To read HDF5 file

# Read CERN ROOT file
#from rootpy.io import ROOTFile # To insert in the secondary libraries
df_root = ROOT.TFile.Open('your_file.root') # To read ROOT file

# Read Feather file
df_feather = pd.read_feather('your_file.feather') # To read Feather file

# Read fixed-width file
#column_widths = [10, 15, 20]    ## To define column widths
df_fixed_width = pd.read_fwf('your_file.txt', widths=column_widths) # To read fixed-width file

# Read data from the clipboard
df_clipboard = pd.read_clipboard() # To read data from the clipboard
```  
### 👁️ 2.2. Initial Exploration - Basic Dataset Structure Overview
#### 2.2.1. Inspect dimensions and dtypes (Variables dictionary with .info(), and deep memory_usage diagnostic)
```python
df.info(memory_usage='deep', show_counts='True')
```  
- 2.2.2. Inspect a fixed amount of random lines with .sample()
```python
df.sample(5)
```  

---

## 🧹 III. Data Cleaning and Transformation - Handling polluted Data 
### 3.1. Manage Missing Values (.isna(), if data missing is >x% or <y%)  
- Best method is to `add dimension` from columns with missing values by creating a `boolean column` (1 for missing values and 0 for values filled)  
- Second method is if data missing is `<30%`, to use `median` or `mode(preferable)` to `fill` missing values  
- Last resort is if data missing is `>30%`, `drop` those rows with .dropna(), for Columns, data missing is `>40%`, .dropna('Columntodrop', axis=1)  
- "These thresholds (e.g. 30% for rows, 40% for columns) are empirical and must be adapted based on domain knowledge, sample size, and model sensitivity."
### 3.2. Handling Duplicate Rows (.duplicated() and .drop_duplicates())  
### 3.3. Handling Outliers (IQR & Z_scores method)  
```python
# Detection made for Distribution Law
z_scores = ((data['column1'] - means) / stds)
z_outliers = (np.abs(z_scores) > zscore_threshold).any(axis=1)

# Detection made for pretty much anything
q1, q3 = np.percentile(df['column1'], [25, 75])
iqr = q3 - q1
lower_bound = q1 - 1.5 * iqr
upper_bound = q3 + 1.5 * iqr
iqr_outliers = df[(df['column1'] >= lower_bound) & (df['column1'] <= upper_bound)]

# Before thinking about removing outliers, check if those outliers are errors, or a valid signal (rare events)
df_no_z_outliers = data[~z_outliers].copy()
df_no_iqr_outliers = df[(df['column1'] >= lower_bound) & (df['column1'] <= upper_bound)].copy()
```  
### 3.4. Data Type Conversion - .astype(), to reduce memory usage, and optimize column distinctions
```python
# Use a dictionnary to store columns as keys, and types you want to set as values
dict_convert = {
    'column1': 'dtypes'
}
# Create a loop to apply .astype(values_from_dict) method
common_cols = set(df.columns) & set(dict_convert.keys())
# Vérifier que les colonnes spécifiées dans le dictionnaire 'conversions' existent bien dans le DataFrame avant de les convertir
for col in common_cols:
    df[col] = df[col].astype(dict_convert[col])
```  
### 3.5. Handling TimeSeries(dates with DateTimeIndex())
```python
df.set_index(df['dateColumn'], inplace = True)
```  

---

## 🧠 IV. Feature Engineering
### 4.1. Creating New Features - Numerical, Categorical and/or TimeSeries
```python
# Comprehension list to sort data types / Timeseries(dates) can be used as index, converted to ordinal/category
timeseries_dtypes = ['datetime64']
numerical_features = df.select_dtypes(include=[np.number]).columns.tolist()
categorical_features = df.select_dtypes(exclude=np.number).columns.tolist()
TimeSeries_features = df.select_dtypes(include=timeseries_dtypes).columns.tolist()
```  
### 4.2. Feature Transformation
#### 4.2.1. Encoding Categorical Variables
[Data Preprocessing Methods](Data_Preprocessing_Methods_Eng.ipynb)
#### 4.2.2. Scaling and Normalization / Standardization Numerical Variables
[Data Preprocessing Methods](Data_Preprocessing_Methods_Eng.ipynb)
#### 4.2.3. Differencing / Characteristic Extraction TimeSeries Variable
[Data Preprocessing Methods](Data_Preprocessing_Methods_Eng.ipynb)

---

## 📈 V. Exploratory Data Analysis - EDA  
### 5.1. Univariate Analysis (Descriptive Statistics)  
#### 5.1.1. Numerical(Quantitative) Features  
```python
# Print the statistics descriptions
```  
#### 5.1.2. Categorical(Qualitative) Features  
```python
# Frequencies, percentages, fractions and/or relative frequencies
```  
#### 5.1.3. TimeSeries(Date) Features
```python
# Resampling(.resample()), Moving Average(.rolling()), Exponential Weighted Function(.ewm())
```
### 5.2. Bivariate / Multivariate Analysis 
#### 5.2.1. Numerical vs Numerical  
```python
# Comparative graphics between 2 or more variables (ScatterPlot, Regression/tendances Curves, BubbleChart, LmPlot, PairPlot, histogram etc...)
```  
#### 5.2.2. Categorical vs Categorical  
```python
# Comparative graphics between 2 or more variables (Groupped/Staked BarChart, MosaicPlot, Heatmap, PairPlot etc...)
```  
#### 5.2.3. Categorical vs Numerical  
```python
# Comparative graphics between 2 or more variables (BoxPlot, ViolinPlot, Mean/error BarChart, Dot/Strip Plot, CatPlot, PairPlot, histogram etc...)
```  
#### 5.2.4. TimeSeries vs Numerical/Categorical  
```python
# Comparative graphics between 2 or more variables (statsmodels.tsa.seasonal_decompose, Histogram, PairPlot etc...)
```  

---

## 🧪 VI. Inferential Analysis  
### 6.1. Hypotheses Definition  
Define your Null-Hypothesis (H0)
### 6.2. Hypothesis Testing  
#### 6.2.1. Normality Hypothesis and Homoscedasticity (homogeneity of variance) Tests (Preliminary tests before choosing Parametric or Non-parametric Tests)
```Python
# Normality Tests: Shapiro-Wilk's Test, Kolmogorov-Smirnov's Test, Anderson-Darling's Test

# Homoscedasticity Tests: Levene's Test, Bartlett's Test

# Autocorrelation Test: Durbin-Watson's Test, White's Test

# Multicollinearity Test: VIF(Variance Inflation Factor)
```  
#### 6.2.2. Parametric Tests (Data without outliers, following Distribution Law)
```python
# For Numerical only data (Correlation Analysis: Pearson's Correlation, Linear Regression T-Test

# For Categorical only data (Confidence Intervals): Logistic Regression, Log-Linear Models

# For Numerical & Categorical data (Variance Analysis): Student's T-Test, MANOVA/ANOVA(Variance Analysis)
```  
#### 6.2.3. Non-parametric Tests (Solid to face data with outlier, and doesn't care of Distribution Law)
```python
# For Numerical only data (Correlation Analysis): Spearman's Correlation, Kendall's(Tau) Correlation

# For Categorical only data (Variance Analysis): Chi², Fisher's Exact Test, NcNemar's Test, Cochran-Armitage's Test for Trends(Correlation Analysis)

# For Numerical & Categorical data (Variance Analysis: Mann-Whitney's  Test, Wilcoxon's Rank-Sum, Kruskal-Wallis's ANOVA
```  
### 6.3. Hypothesis Conclusion
#### 6.3.1. H0 or H1 is valide  
#### 6.3.2. Feature Selection  
```python
# From various tests, which columns will you keep ?
df = df[['column1', 'column2', '...', 'columnN']]
# If you have more column to keep than to drop, which columns will you drop ?
df = df.drop(['column1', 'Column2', '...', 'columnN'], axis=1])
```

---

## 🤖 VII. Predictive Modeling
### 7.1. Data Preprocessing for Modeling
#### 7.1.1. Features / Target Separation  
```python
# Features & Target
X = df.drop(['TargetColumn'], axis=1)
y = df[['TargetColumn']]
```  
#### 7.1.2. Train-Test Split (train_test_split as tts) and TimeSeries Split (TimeSeriesSplit as tss)
```python
# Common partition is 80/20 (80% for Train and 20% for Test), Shuffle should be set as True
X_train, X_test, y_train, y_test = tts(X, y, train_size=0.8, random_state=1, shuffle=True, stratify=None)
```  
#### 7.1.3. Cross-Validation Strategy (Hyperparameter Tuning)  
```python
# Global Hyperparameters: Grid Search (GridSearchCV), Randomized Search (RandomizedSearchCV), Bayesian Optimization (BayesianSearchCV Optuna, Hyperopt)

# Regression only Hyperparameter: Cross-validation integrated tuning

# Classifier only Hyperparameter: Cross-validation with stratified sampling (StratifiedKFold)
```  
### 7.2. Model Training & Evaluation
#### 7.2.1. Model Training on Train Set  
```python
# Regressors (e.g., Linear Regression, Random Forest Regressor, Gradient Boosting Regressor...)

# Classifiers (e.g., Logistic Regression, Decision Trees, Random Forest Classifier, Support Vector Machines)

# Pipelines for preprocessing and training

# Cross-validation techniques (e.g., Group/K Fold, StratifiedKFold, TimeSeriesSplit for sequential data)
```  
#### 7.2.2. Error Analysis and Metrics  
```python
# Regression Metrics: Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), R-squared (R²)

# Classifier Analysis: Accuracy, Precision, Recall, F1-Score and Visual Error Analysis like Confusion Matrix, ROC Curve / AUC, Precision-Recall Curves
```  
#### 7.2.3. Visual Evaluation  
```python
# Regression: Scatter Plots (actual vs. predicted), Line Plots, Residual Plots, Learning Curves, Box Plots

# Classifier: Heatmaps (for Confusion Matrices), ROC Curves, Precision-Recall Curves
```  
### 7.3. Generalization & Real Use Cases
#### 7.3.1. Prediction on Real Test Sets
```python
# Inference on unseen/real-world data using the trained model

# Utilize preprocessing/feature engineering pipelines on real test data

# Generate predictions via model.predict (batch or streaming)

# Perform final evaluation and error analysis on real test set performance
```  
#### 7.3.2. Deployment Considerations (optional)
```python
# Model serialization and export (e.g., pickle, joblib, ONNX, SavedModel)

# API deployment frameworks (e.g., Flask, FastAPI, TensorFlow Serving, TorchServe)

# Containerization and orchestration (e.g., Docker, Kubernetes)

# Monitoring, logging, and performance tuning for production
```  

---

## 📌 VIII. Prescriptive Analysis  
### 8.1. Business Recommendations 
- Translate analytical insights into actionable strategies.
- Leverage data storytelling to inform strategic decision-making.
- Utilize frameworks such as SWOT analysis, KPI definition, and performance monitoring.
- Engage with domain experts to validate recommendations.
### 8.2. What-if Scenarios / Simulations  
- Develop simulation models to explore alternative future scenarios.
- Employ methods like Monte Carlo simulations and sensitivity analysis.
- Use scenario planning to assess the impact of varying assumptions.
- Evaluate risk and uncertainty across different operational or market situations.
### 8.3. Dashboard Design (Optional for Stakeholders)  
- Build interactive and informative dashboards for real-time data visualization.
- Use tools such as Tableau, PowerBI, or Plotly Dash for ease-of-use and accessibility.
- Focus on user-centric design principles: clarity, simplicity, and actionable insights.
- Ensure scalability, maintainability, and data security in dashboard deployment.

---

🎉 Congratulations on completing this end-to-end data science guide!  
You're now ready to take the next step and publish your project.  
Head over to the [Git & GitHub Environment](../Git_GitHub/01-Github_Git_Init.md) to learn how to upload your work on GitHub and make it shareable.  

_Edited: 2025-04-22_