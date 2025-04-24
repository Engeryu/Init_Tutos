# Numpy & Pandas Methods
**Author:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

Voici la version française du document [NumPy & Pandas CheatSheet](./NumPy_Pandas_CheatSheet_FR.md)

## Table of contents
- [Pandas Methods](#Pandas-Methods)
  - [Data Inspection](#Data-Inspection)
  - [Data Cleaning](#Data-Cleaning)
  - [Data Manipulation](#Data-Manipulation)
  - [Aggregation and Grouping](#Aggregation-and-Grouping)
  - [Merging and Joining](#Merging-and-Joining)
  - [Reshaping](#Reshaping)
  - [Statistical Methods](#Statistical-Methods)
- [NumPy Methods](#NumPy-Methods)
  - [Array Creation](#Array-Creation)
  - [Array Manipulation](#Array-Manipulation)
  - [Mathematical Functions](#Mathematical-Functions)
  - [Statistical Functions](#Statistical-Functions)
  - [Linear Algebra](#Linear-Algebra)

---

## Pandas Methods

### Data Inspection

| Method            | Description                                |
|------------------|---------------------------------------------|
| `.head()`        | Returns first n rows                        |
| `.tail()`        | Returns last n rows                         |
| `.info()`        | Provides a summary of the DataFrame         |
| `.describe()`    | Generates descriptive statistics            |
| `.shape`         | Returns a tuple of dimensions               |
| `.dtypes`        | Returns data types of each column           |
| `.columns`       | Lists column names                          |
| `.index`         | Returns the index (row labels)              |
| `.sample()`      | Returns a random sample                     |

### Data Cleaning

| Method               | Description                                |
|---------------------|---------------------------------------------|
| `.isna()`           | Detects missing values (isnull() is an alias of isna() |
| `.notnull()`        | Detects non-missing values                  |
| `.dropna()`         | Removes missing values                      |
| `.fillna()`         | Fills missing values                        |
| `.astype()`         | Converts data types                         |
| `.replace()`        | Replaces values                             |
| `.duplicated()`     | Checks for duplicate rows                   |
| `.drop_duplicates()`| Removes duplicate rows                      |

### Data Manipulation

| Method              | Description                                |
|--------------------|---------------------------------------------|
| `.sort_values()`   | Sorts by values                             |
| `.sort_index()`    | Sorts by index                              |
| `.rename()`        | Renames axes                                |
| `.apply()`         | Applies a function                          |
| `.map()`           | Maps values (Series only)                   |
| `.applymap()`      | Applies function element-wise (DataFrame)   |
| `.assign()`        | Assigns new columns                         |
| `.query()`         | Queries the data using a string expression  |

### Aggregation and Grouping

| Method             | Description                                |
|--------------------|--------------------------------------------|
| `.groupby()`       | Groups data for aggregation                |
| `.agg()`           | Aggregates using one or more operations    |
| `.mean()`          | Calculates mean                            |
| `.sum()`           | Calculates sum                             |
| `.count()`         | Counts non-null values                     |
| `.min()` / `.max()`| Minimum and maximum values                 |
| `.value_counts()`  | Counts unique values (Series only)         |

### Merging and Joining

| Method             | Description                                 |
|--------------------|---------------------------------------------|
| `pd.merge()`       | Merges DataFrames horizontally              |
| `.join()`          | Joins columns with another DataFrame        |
| `pd.concat()`      | Concatenates along a particular axis        |
| `.append()`        | Appends rows (deprecated in v2.0+)          |

### Reshaping

| Method             | Description                                 |
|--------------------|---------------------------------------------|
| `.pivot()`         | Reshapes data by column values              |
| `.pivot_table()`   | Creates a pivot table with aggregation      |
| `.melt()`          | Unpivots columns into rows                  |
| `.stack()`         | Stacks columns into index                   |
| `.unstack()`       | Unstacks index into columns                 |
| `.transpose()`     | Transposes rows and columns                 |
| `.T`               | Shortcut for transpose                      |

### Statistical Methods

| Method             | Description                                |
|-------------------|---------------------------------------------|
| `.mean()`          | Arithmetic mean                            |
| `.median()`        | Median value                               |
| `.mode()`          | Mode value                                 |
| `.std()`           | Standard deviation                         |
| `.var()`           | Variance                                   |
| `.corr()`          | Correlation matrix                         |
| `.cov()`           | Covariance matrix                          |

---

## NumPy Methods

### Array Creation

| Method              | Description                                  |
|--------------------|-----------------------------------------------|
| `np.array()`        | Creates an array from a list or tuple         |
| `np.zeros()`        | Creates array of zeros                        |
| `np.ones()`         | Creates array of ones                         |
| `np.full()`         | Creates array with a constant value           |
| `np.arange()`       | Creates array with evenly spaced values       |
| `np.linspace()`     | Creates array with fixed number of values     |
| `np.eye()`          | Identity matrix                               |
| `np.random.rand()`  | Random values (uniform distribution)          |
| `np.random.randn()` | Random values (normal distribution)           |
| `np.random.randint()`| Random integers in a range                   |

### Array Manipulation

| Method              | Description                                   |
|---------------------|-----------------------------------------------|
| `.reshape()`        | Changes shape without changing data           |
| `.ravel()`          | Flattens the array                            |
| `.flatten()`        | Flattens the array (returns a copy)           |
| `.transpose()`      | Permutes dimensions of array                  |
| `.T`                | Shortcut for transpose                        |
| `.concatenate()`    | Joins a sequence of arrays                    |
| `.stack()`          | Stacks arrays vertically or horizontally      |
| `.hstack()` / `.vstack()` | Horizontal / Vertical stacking          |
| `.split()`          | Splits array into multiple sub-arrays         |

### Mathematical Functions

| Method              | Description                                   |
|---------------------|-----------------------------------------------|
| `np.add()`          | Element-wise addition                         |
| `np.subtract()`     | Element-wise subtraction                      |
| `np.multiply()`     | Element-wise multiplication                   |
| `np.divide()`       | Element-wise division                         |
| `np.power()`        | Element-wise power                            |
| `np.sqrt()`         | Square root                                   |
| `np.exp()`          | Exponential                                   |
| `np.log()`          | Natural logarithm                             |
| `np.abs()`          | Absolute value                                |

### Statistical Functions

| Method              | Description                                  |
|--------------------|-----------------------------------------------|
| `np.mean()`         | Mean of elements                             |
| `np.median()`       | Median value                                 |
| `np.std()`          | Standard deviation                           |
| `np.var()`          | Variance                                     |
| `np.min()` / `np.max()`| Min/Max values                            |
| `np.percentile()`   | Percentile value                             |
| `np.corrcoef()`     | Correlation coefficients                     |

### Linear Algebra

| Method              | Description                                   |
|---------------------|-----------------------------------------------|
| `np.dot()`          | Dot product of two arrays                     |
| `np.matmul()`       | Matrix multiplication                         |
| `np.linalg.inv()`   | Inverse of a matrix                           |
| `np.linalg.det()`   | Determinant of a matrix                       |
| `np.linalg.eig()`   | Eigenvalues and eigenvectors                  |
| `np.linalg.norm()`  | Matrix or vector norm                         |

---

**You can redirect to [Data Preprocessing Methods](Data_Preprocessing_Methods_Eng.ipynb) CheatSheet**

_Edited: 2025/04/22_