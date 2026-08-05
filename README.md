# Student Performance Prediction using Linear Regression

> An end-to-end Machine Learning project that predicts a student's final academic performance using Linear Regression while demonstrating the complete Data Science workflow, from Exploratory Data Analysis (EDA) to model evaluation.

![Python](https://img.shields.io/badge/Python-3.11+-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-013243?logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?logo=scikitlearn)

---

## Project Overview

Student performance is influenced by several academic, personal, and social factors. This project aims to build a **Linear Regression model** capable of predicting a student's final grade (**G3**) based on multiple features such as study time, attendance, previous grades, family support, health, and more.

Rather than focusing only on model training, this project emphasizes understanding the **mathematics**, **statistics**, and **theory** behind every stage of the Machine Learning pipeline.

---

## Objectives

- Understand the dataset and each feature in detail.
- Perform comprehensive Exploratory Data Analysis (EDA).
- Analyze feature relationships using statistical methods.
- Apply appropriate preprocessing techniques.
- Build and interpret a Linear Regression model.
- Evaluate model performance using multiple regression metrics.
- Explain the mathematics behind every step instead of treating Machine Learning as a black box.

---

## Dataset

**Dataset:** Student Performance Dataset (UCI Machine Learning Repository)

- Two datasets are provided:
  - Mathematics Students (`student-mat.csv`)
  - Portuguese Language Students (`student-por.csv`)

This project uses:

**`student-por.csv`**

Target Variable:

```
G3 (Final Grade)
```

---

## Machine Learning Pipeline

```
Raw Dataset
      │
      ▼
Data Understanding
      │
      ▼
Exploratory Data Analysis (EDA)
      │
      ▼
Data Preprocessing
      │
      ▼
Feature Engineering
      │
      ▼
Correlation Analysis
      │
      ▼
Train-Test Split
      │
      ▼
Linear Regression
      │
      ▼
Prediction
      │
      ▼
Model Evaluation
```

---

## Topics Covered

### Exploratory Data Analysis

- Dataset overview
- Missing value analysis
- Duplicate detection
- Descriptive statistics
- Distribution analysis
- Outlier detection
- Feature relationships

---

### Data Preprocessing

- Handling missing values
- Encoding categorical variables
- Feature scaling
- Data cleaning
- Train-Test Split

---

### Statistical Analysis

- Mean
- Median
- Mode
- Variance
- Standard Deviation
- Covariance
- Pearson Correlation
- Correlation Matrix

---

### Machine Learning

- Linear Regression
- Least Squares Method
- Model Training
- Prediction
- Residual Analysis

---

### Evaluation Metrics

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

---

## Project Structure

```
Student-Performance-Prediction/
│
├── data/
│   ├── raw/
│   │   ├── student-por.csv
│   │   └── student.txt
│   │
│   └── processed/
│
├── notebooks/
│   ├── 01_Data_Understanding.ipynb
│   ├── 02_EDA.ipynb
│   ├── 03_Preprocessing.ipynb
│   ├── 04_Model_Training.ipynb
│   └── 05_Model_Evaluation.ipynb
│
├── reports/
│   ├── figures/
│   └── results/
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## Mathematical Concepts

This project explains the mathematics behind Machine Learning, including:

- Linear Equations
- Feature Vectors
- Least Squares Regression
- Cost Functions
- Residuals
- Correlation
- Statistical Measures
- Regression Metrics

---

## Expected Visualizations

- Histograms
- Box Plots
- Count Plots
- Correlation Heatmap
- Pair Plot
- Scatter Plots
- Residual Plot
- Prediction vs Actual Plot

---

## Author

**Soumya Prakash Jena**

GitHub: https://github.com/buildwithsoumya

---

If you found this project useful, consider giving it a star!