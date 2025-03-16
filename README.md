# 🚀 Data Wrangling Using Python

## 🎯 Objectives

- ✅ Handle missing values
- ✅ Correct data formatting
- ✅ Standardize and normalize data

## 🔍 What is Data Wrangling?
Data wrangling is the process of transforming raw data into a more useful format for analysis. It includes handling missing values, correcting data formats, normalizing values, and more.

---

## 🔎 Handling Missing Values
Missing values can impact data analysis. We can identify and handle them using Pandas.

### 🛠 Steps for Working with Missing Data
1. **Identify missing data**
2. **Deal with missing data**
3. **Correct data format**

### 🔹 Identify Missing Values
In Pandas, we can detect missing values using:
```python
# Check for missing values
 df.isnull()
 df.notnull()
```

### 🔹 Convert `?` to NaN
In datasets, missing values may be represented by `?`. We can replace them with `NaN`:
```python
import numpy as np
 df.replace("?", np.nan, inplace=True)
```

### 🔹 Dealing with Missing Data
We can handle missing data in different ways:
- **Drop Data**
  - 🔻 Drop the whole row
  - 🔻 Drop the whole column
- **Replace Data**
  - 🔄 Replace with **mean**
  - 🔄 Replace with **most frequent value**
  - 🔄 Replace using **other functions**

---

## 📏 Correcting Data Format
Ensuring that all data is in the correct format is crucial for analysis.

### 🔹 Checking Data Type
```python
df.dtypes
```

### 🔹 Converting Data Type
```python
df["column_name"] = df["column_name"].astype("desired_type")
```

---

## 📊 Data Normalization
### 🤔 Why Normalize?
Normalization helps scale values to a consistent range, making comparisons easier. Common techniques:
- **Mean normalization** (scaling to average = 0)
- **Variance normalization** (scaling to variance = 1)
- **Min-Max scaling** (scaling values from 0 to 1)

### 🔹 Example: Min-Max Scaling
```python
df['normalized_column'] = df['column_name'] / df['column_name'].max()
```

---

## 📦 Binning
### 🤔 Why Binning?
Binning groups continuous numerical values into discrete categories.

### 🔹 Example: Binning Horsepower into 3 Categories
```python
bins = np.linspace(min(df["horsepower"]), max(df["horsepower"]), 4)
group_names = ["Low", "Medium", "High"]
df['horsepower-binned'] = pd.cut(df['horsepower'], bins, labels=group_names, include_lowest=True)
```

---

## 🏷️ Indicator (Dummy) Variables
### 🤔 What Are Indicator Variables?
Dummy variables convert categorical values into numerical labels for regression analysis.

### 🔹 Example: Converting `fuel-type` to Dummy Variables
```python
dummies = pd.get_dummies(df["fuel-type"])
df = pd.concat([df, dummies], axis=1)
df.drop("fuel-type", axis=1, inplace=True)
```

---

## 🎉 Conclusion
By completing this lab, you now understand how to:
✔ Handle missing data
✔ Correct data formatting
✔ Normalize and standardize data
✔ Use binning for grouped analysis
✔ Convert categorical data into numerical dummy variables


