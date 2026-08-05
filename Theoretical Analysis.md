# Student Performance Prediction: Mathematical Foundations

> A concise mathematical companion to an end-to-end linear-regression project using the UCI Student Performance dataset.

---

## 1. Understanding the Dataset

### Objective

Predict a student's final grade, $G3$, from demographic, academic, family, and lifestyle features.

### Dataset at a glance

| Item | Value |
| --- | --- |
| Dataset file | `student-por.csv` |
| Observations | 649 students |
| Input features | 32 |
| Target | $G3$ |

### Machine-learning representation

Let $m$ denote the number of students and $n$ the number of input features. The design matrix is

$$
\mathbf{X} =
\begin{bmatrix}
x_{11} & x_{12} & \cdots & x_{1n} \\
x_{21} & x_{22} & \cdots & x_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
x_{m1} & x_{m2} & \cdots & x_{mn}
\end{bmatrix}
\in \mathbb{R}^{m \times n}.
$$

The target vector is

$$
\mathbf{y} =
\begin{bmatrix}
G3_1 \\
G3_2 \\
\vdots \\
G3_m
\end{bmatrix}
\in \mathbb{R}^{m}.
$$

Each row of $\mathbf{X}$ represents one student, and each column represents one feature.

---

## 2. Mathematics of Linear Regression

### Simple linear regression

For one predictor $x$, the predicted value is

$$
\hat{y} = mx + c,
$$

where $m$ is the slope and $c$ is the intercept.

### Multiple linear regression

With $n$ predictors, the model for a single observation is

$$
\hat{y} = w_1x_1 + w_2x_2 + \cdots + w_nx_n + b.
$$

In vector form for the full dataset:

$$
\hat{\mathbf{y}} = \mathbf{X}\mathbf{w} + b\mathbf{1},
$$

where $\mathbf{w} \in \mathbb{R}^{n}$ is the coefficient vector, $b$ is the intercept, and $\mathbf{1}$ is an $m$-dimensional vector of ones.

### Residuals

The residual vector measures prediction error:

$$
\mathbf{e} = \mathbf{y} - \hat{\mathbf{y}}.
$$

### Least-squares objective

Linear regression chooses parameters that minimize the average squared residual:

$$
J(\mathbf{w}, b) = \frac{1}{m}\sum_{i=1}^{m}\left(y_i - \hat{y}_i\right)^2.
$$

$$
\min_{\mathbf{w},\,b} \quad J(\mathbf{w}, b).
$$

#### Why square the error?

- It prevents positive and negative errors from cancelling each other out.
- It gives greater weight to larger mistakes.
- It produces a smooth, differentiable optimization objective.

### Learning process

```text
Initialize weights → Predict → Compute residuals → Compute cost
        ↑                                             │
        └──────────── Update weights ←────────────────┘
                    (repeat until convergence)
```

---

## 3. Statistics Behind Exploratory Data Analysis

### Mean

$$
\bar{x} = \frac{1}{n}\sum_{i=1}^{n} x_i.
$$

### Median

The middle value after sorting the observations. It is less sensitive to outliers than the mean.

### Variance

$$
\sigma^2 = \frac{1}{n}\sum_{i=1}^{n}\left(x_i - \bar{x}\right)^2.
$$

Variance measures the spread of values around their mean.

### Standard deviation

$$
\sigma = \sqrt{\sigma^2}.
$$

### Covariance

$$
\mathrm{Cov}(X,Y) = \frac{1}{n}\sum_{i=1}^{n}
\left(x_i - \bar{x}\right)\left(y_i - \bar{y}\right).
$$

A positive covariance indicates that the variables tend to increase together.

### Pearson correlation

$$
r_{X,Y} = \frac{\mathrm{Cov}(X,Y)}{\sigma_X\sigma_Y}.
$$

| Correlation | Interpretation |
| ---: | --- |
| $+1$ | Perfect positive linear relationship |
| $0$ | No linear relationship |
| $-1$ | Perfect negative linear relationship |

### Typical EDA flow

```text
Load data → Inspect shape & types → Check missing values
    → Summarize statistics → Visualize distributions
    → Analyze correlations → Detect outliers
```

Useful visualizations include histograms, box plots, scatter plots, correlation heatmaps, and pair plots.

---

## 4. Data Preprocessing

### Missing values

Mean imputation replaces a missing value with

$$
\bar{x} = \frac{x_1 + x_2 + \cdots + x_n}{n}.
$$

Median imputation is often preferable when the feature contains substantial outliers.

### Encoding categorical variables

Models require numeric inputs. Common approaches are:

- **Label encoding** — maps each category to an integer.
- **One-hot encoding** — creates a binary indicator column for each category.

### Feature scaling

**Min–max scaling** maps a value to a chosen range, usually $[0,1]$:

$$
x' = \frac{x - x_{\min}}{x_{\max} - x_{\min}}.
$$

**Standardization** expresses a value in standard deviations from the mean:

$$
z = \frac{x - \mu}{\sigma}.
$$

### Train–test split

A typical split uses 80% of the data for training and 20% for testing. Keep the test set isolated during training to avoid **data leakage**.

---

## 5. Model Evaluation

Let $y_i$ be the actual value and $\hat{y}_i$ the prediction for observation $i$.

### Mean absolute error

$$
\mathrm{MAE} = \frac{1}{m}\sum_{i=1}^{m}\left|y_i - \hat{y}_i\right|.
$$

### Mean squared error

$$
\mathrm{MSE} = \frac{1}{m}\sum_{i=1}^{m}\left(y_i - \hat{y}_i\right)^2.
$$

### Root mean squared error

$$
\mathrm{RMSE} = \sqrt{\mathrm{MSE}}.
$$

Lower MAE, MSE, and RMSE indicate more accurate predictions.

### Coefficient of determination

$$
R^2 = 1 - \frac{SS_{\mathrm{res}}}{SS_{\mathrm{tot}}},
$$

where

$$
SS_{\mathrm{res}} = \sum_{i=1}^{m}\left(y_i - \hat{y}_i\right)^2,
\qquad
SS_{\mathrm{tot}} = \sum_{i=1}^{m}\left(y_i - \bar{y}\right)^2.
$$

| $R^2$ value | Meaning |
| ---: | --- |
| $1$ | Perfect prediction |
| $0$ | No better than predicting the mean |
| $< 0$ | Worse than the mean predictor |

---

## Complete Project Pipeline

```text
Dataset → Data Understanding → EDA → Preprocessing → Feature Selection
    → Train/Test Split → Linear Regression → Prediction
    → MAE • MSE • RMSE • R² → Interpret Results
```

## Interview Notes

- Explain the purpose of every preprocessing step.
- Justify why linear regression is appropriate for the target and features.
- Interpret model coefficients rather than reporting metrics alone.
- Discuss the core assumptions: linearity, independence, homoscedasticity, approximately normal residuals, and low multicollinearity.

## Possible Extensions

- Polynomial regression
- Ridge regression
- Lasso regression
- Feature engineering
- Cross-validation
- Residual diagnostics
- Hyperparameter tuning
- Model deployment
