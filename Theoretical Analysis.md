# Student Performance Prediction --- Mathematical Foundations

> Comprehensive study notes for an end-to-end Linear Regression project
> using the UCI Student Performance Dataset.

------------------------------------------------------------------------

# Chapter 1 --- Understanding the Dataset

## Objective

Predict the final grade (**G3**) of a student from demographic,
academic, family and lifestyle features.

## Dataset

-   Samples: **649 students** (`student-por.csv`)
-   Features: **32 input features**
-   Target: **G3**

## Machine Learning Representation

Let

\[ X =
```{=tex}
\begin{bmatrix}
x_{11} & x_{12} & \cdots & x_{1n}\\
x_{21} & x_{22} & \cdots & x_{2n}\\
\vdots & \vdots & \ddots & \vdots\\
x_{m1} & x_{m2} & \cdots & x_{mn}
\end{bmatrix}
```
\]

Target

\[ y=
```{=tex}
\begin{bmatrix}
G3_1\\
G3_2\\
\vdots\\
G3_m
\end{bmatrix}
```
\]

Each row is one student (observation). Each column is one feature.

------------------------------------------------------------------------

# Chapter 2 --- Mathematics of Linear Regression

## Simple Linear Regression

\[ y = mx + c \]

where

-   (m): slope
-   (c): intercept

## Multiple Linear Regression

\[ `\hat `{=tex}y=w_1x_1+w_2x_2+`\cdots`{=tex}+w_nx_n+b \]

Vector notation

\[ `\hat `{=tex}y=Xw+b \]

## Residual

\[ e=y-`\hat `{=tex}y \]

## Least Squares Objective

\[ J(w,b)=`\frac`{=tex}1n`\sum`{=tex}\_{i=1}^{n}(y_i-`\hat `{=tex}y_i)^2
\]

The objective is

\[ `\min`{=tex}\_{w,b}J(w,b) \]

### Why square the error?

-   Prevent positive and negative errors from cancelling.
-   Penalize larger mistakes more heavily.
-   Produces a differentiable objective.

### Learning Process

``` text
Initialize weights
      │
      ▼
Predict
      │
      ▼
Compute residuals
      │
      ▼
Compute cost
      │
      ▼
Update weights
      │
      ▼
Repeat until convergence
```

------------------------------------------------------------------------

# Chapter 3 --- Statistics Behind EDA

## Mean

\[ `\bar `{=tex}x=`\frac`{=tex}1n`\sum `{=tex}x_i \]

## Median

Middle value after sorting.

## Variance

\[ `\sigma`{=tex}^2=`\frac`{=tex}1n`\sum`{=tex}(x_i-`\bar `{=tex}x)^2 \]

Measures spread.

## Standard Deviation

\[ `\sigma`{=tex}=`\sqrt{\sigma^2}`{=tex} \]

## Covariance

\[
Cov(X,Y)=`\frac`{=tex}1n`\sum`{=tex}(x_i-`\bar `{=tex}x)(y_i-`\bar `{=tex}y)
\]

Positive covariance → variables increase together.

## Pearson Correlation

\[ r=`\frac{Cov(X,Y)}{\sigma_X\sigma_Y}`{=tex} \]

Range:

-   +1 Perfect positive
-   0 No linear relation
-   -1 Perfect negative

### Typical EDA Flow

``` text
Load Data
    │
    ▼
Shape & Types
    │
    ▼
Missing Values
    │
    ▼
Summary Statistics
    │
    ▼
Distributions
    │
    ▼
Correlation Matrix
    │
    ▼
Outlier Detection
```

Suggested plots:

-   Histogram
-   Box Plot
-   Scatter Plot
-   Correlation Heatmap
-   Pair Plot

------------------------------------------------------------------------

# Chapter 4 --- Data Preprocessing

## Missing Values

Mean

\[ x=`\frac{x_1+x_2+\cdots+x_n}{n}`{=tex} \]

Median is preferred when outliers exist.

## Encoding

Convert categorical variables into numbers.

Examples:

-   Label Encoding
-   One-Hot Encoding

## Feature Scaling

### Min-Max Scaling

\[ x'=`\frac{x-x_{min}}{x_{max}-x_{min}}`{=tex} \]

### Standardization

\[ z=`\frac{x-\mu}{\sigma}`{=tex} \]

## Train-Test Split

Typical split

-   80% Training
-   20% Testing

Never use test data during training to avoid **data leakage**.

------------------------------------------------------------------------

# Chapter 5 --- Model Evaluation

## Mean Absolute Error

\[ MAE=`\frac`{=tex}1n`\sum`{=tex}\|y-`\hat `{=tex}y\| \]

## Mean Squared Error

\[ MSE=`\frac`{=tex}1n`\sum`{=tex}(y-`\hat `{=tex}y)\^2 \]

## Root Mean Squared Error

\[ RMSE=`\sqrt{MSE}`{=tex} \]

Lower RMSE indicates better predictions.

## Coefficient of Determination

\[ R\^2=1-`\frac{SS_{res}}{SS_{tot}}`{=tex} \]

Interpretation

  R²    Meaning
  ----- -------------------------------
  1     Perfect prediction
  0     Same as predicting the mean
  \<0   Worse than the mean predictor

------------------------------------------------------------------------

# Complete Project Pipeline

``` text
Dataset
   │
   ▼
Data Understanding
   │
   ▼
EDA
   │
   ▼
Preprocessing
   │
   ▼
Feature Selection
   │
   ▼
Train/Test Split
   │
   ▼
Linear Regression
   │
   ▼
Prediction
   │
   ▼
MAE • MSE • RMSE • R²
   │
   ▼
Interpret Results
```

# Interview Notes

-   Explain every preprocessing step.
-   Justify why Linear Regression is appropriate.
-   Interpret coefficients instead of only reporting metrics.
-   Discuss assumptions:
    -   Linearity
    -   Independence
    -   Homoscedasticity
    -   Approximately normal residuals
    -   Low multicollinearity

# Next Expansion

Future versions can add: - Polynomial Regression - Ridge Regression -
Lasso Regression - Feature Engineering - Cross Validation - Residual
Diagnostics - Hyperparameter Tuning - Model Deployment
