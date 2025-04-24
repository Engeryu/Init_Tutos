# Data Preprocessing Methods
**Author:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

## Table of Contents
- [Feature Engineering](#Feature-Engineering)
  - [Scaling, Normalization, and Standardization](#Scaling-Normalization-and-Standardization)
- [Encoding Categorical Features](#Encoding-Categorical-Features)
- [Data Splitting](#Data-Splitting)
- [Preprocessing Utilities](#Preprocessing-Utilities)

---

## Preprocessing Utilities

| Tool / Concept                              | Description                                  |
|---------------------------------------------|----------------------------------------------|
| `fit()` / `transform()` / `fit_transform()` | Methods used to apply transformations        |
| `Pipeline` (sklearn)                        | Chains preprocessing steps and models        |
| `ColumnTransformer` (sklearn)               | Applies transformers to specific columns     |
| `FunctionTransformer`                       | Wraps custom functions into a transformer    |

---

## Feature Engineering

### Scaling, Normalization and Standardization

| Method / Tool (Sklearn only)        | Description                                        |
|-------------------------------------|----------------------------------------------------|
| `MinMaxScaler` (sklearn)            | Scales features to a 0–1 range                     |
| `StandardScaler` (sklearn)          | Standardizes features (mean = 0, std = 1)          |
| `RobustScaler` (sklearn)            | Scales using median and IQR (robust to outliers)   |
| `Normalizer` (sklearn)              | Normalizes samples individually to unit norm       |

---

## Encoding Categorical Features

| Method / Tool              | Description                                          |
|----------------------------|------------------------------------------------------|
| `OrdinalEncoder` (sklearn) | Encodes ordinal features with ordered integers       |
| `LabelEncoder` (sklearn)   | Encode ordinal/ranking categories data               |
| `pd.get_dummies()` \ `OneHotEncoder` (sklearn) | Encode nominal categories data |

---

## Data Splitting

| Method / Tool (Sklearn only)         | Description                                                                                |
|-------------------------------|----------------------------------------------------------------------------|
| `train_test_split()`          | Splits dataset into train/test subsets (Normal-size dataset splitter) |
| `StratifiedKFold`             | Maintains class proportions across folds (Bigger-size classification target splitter) |
| `KFold` / `GroupKFold`        | Cross-validation methods with or without grouping (Bigger-size regression target splitter) |
| `TimeSeriesSplit`             | Cross-validation method made for datasets including a date you set as index |

---

## Utilitaires de Prétraitement

| Tools / Concept                             | Description                                 |
| ---                                         | ---                                         |
| `fit()` / `transform()` / `fit_transform()` | Methods for applying transformations        |
| `Pipeline` (sklearn)                        | Chains preprocessing and modeling steps     |
| `ColumnTransformer` (sklearn)               | Applies transformers to specific columns    |
| `FunctionTransformer`                       | Integrates custom functions into a pipeline |


---

**You can redirect to the final sheet about [End-To-End Data Science Workflow](End-to-End_Data_Science_Workflow_Eng.ipynb)**

_Edited: 2025/04/22_
